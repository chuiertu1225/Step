- 序  
  >神在细节之中
- 前言  
  糟糕的代码能毁一家公司，很多人因为时间缘故没有时间清理代码。
  >勒布朗法则：稍后等于永不
- ### 第一章 整洁代码
  > 我喜欢优雅高效的代码，代码逻辑应当直截了当，叫缺陷难以隐藏；尽量减少依赖关系，使之便于维护；根据某种分层战略完善错误处理代码；性能调至最优，省得引诱别人做没规矩的优化，搞出一堆混乱来。**整洁的代码只做好一件事**。    -- c++之父 Bjarne Stroustrup  
  
  本章引用了一些知名程序员对整洁的看法，有人做了重要排序：1.能通过所有测试 2.没有重复代码 3.体现系统中的全部设计理念 4.包括尽量少的实体，比如类、方法、函数等。

- ### 第二章 有意义的命名
    - ### 见名知义  
            public List<int[]> getThem() {
                List<int[]> list1 = new ArrayLIst<int[]>();
                for (int[] x: theList)
                    if(x[0] == 4)
                        list1.add(x);
                return list1;
            }
        这段代码有四处问题：1.theList是什么类型 2.thisList零下标条目的意义是什么 3.值4的意义是什么 4.我怎么使用返回的列表

            public List<Cell> getFlaggedCells() {
                List<Cell> flaggedCells = new ArrayList<Cell>();
                for(Cell cell: gameBoard)
                    if(cell.isFlagged())
                        flaggedCells.add(cell);
                return flaggedCells;
            }
        这是扫雷游戏，盘面是theList的单元格列表，更名为gameBoard,零下标是一种状态值，可以写为cell[STATUS_VALUE] == FLAGGED，状态值4为已标记。不过可以将此状态封装到Cell取代int[]类中
    - ### 避免误导
        1. 带list、class等特殊意义的命名
        2. l和1，O和0易混淆的
    
    - ### 意义区分       
            getActiveAccount();
            getActiveAccounts();
            getActiveAccountInfo();
        缺少明确规定，class的命名就没区别，意义含混不清

    - ### 易懂可搜
        按常规命名，能念出来拼出来最好  
        命名最好全文可搜索，不好搜索的比如data、e等

    - ### 表达一致
        用fetch、retrive、get其中之一来表达获取，同理还有controller、manager、driver

    - ### 语境变量
        对于多步骤的长函数，对于每个步骤抽象成方法，命名符合上下文语境

- ## 第三章 函数
    - ### 短小精简
        缩进层级不应多于一级或两级
    - ### 单一职责
        函数只做好一件事
    - ### switch语句
            public Money calculatePay(Employee e) throws InvalidEmployeeType{
                switch(e.type){
                    case COMMISSION:
                        return calculateComminsionedPay(e);
                    case HOURLY:
                        return calculateHourlyPay(e);
                    case SALARIED:
                        return calculateSalariedPay(e);
                    default:
                        throw new InvalidEmployeeType(e.Type);
                }
            }
        问题：1.太长，出现新雇员类型则更长 2.违反单一权责原则 3.违反开放闭合原则，添加新类型时，必须修改它 4.使得出现类似 `isPayday(Employee e, Date date)`的函数  D
        解决方法：将switch语句埋到抽象工厂下面，不同的函数如`caculatePay、isPayDay`等由Employee接口多态地派遣

            puvlic abstract class Employee{
                public abstract boolean isPayDay();
                ...
            }
            public interface EmployeeFactory{
                public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
            }
            public class EmployeeFactoryImp implements EmployeeFactory{
                public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType{
                    switch(r.type){
                        case COMMISSION:
                            return commsionsionedEmployee(r);
                        case HOURLY:
                            return hourlyEmployee(r);
                        case SALARIED:
                            return salariedEmployee(r);
                    default:
                        throw new InvalidEmployeeType(e.Type);
                    }
                }
            }

    - ### 善用描述
        不畏长名称，不畏花时间    
    - ### 函数参数
        尽量避免三个及以上       
    - ### 指令询问
        分离指令和询问。`if (set("username","unclebob"))`这句是问username属性是否之前已设置为unclebob或者username属性值是否成功设置为unclebob，很难判断，分离开来防止混淆
            
                if(atrributeExists("username")){
                    setAttribute("username","unclebob")
                }
    - ### 异常错误
        用异常代替返回错误码，try...catch语句最好将主体抽离出来
    - ### DRY
        don`t repeat yourself
    
  
  
  
  

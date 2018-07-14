## dbutils使用---QueryRunner、BeanListHandler、BeanHandler、MapListHandler、MapHandler、ScalarHandler
1. ResultSetHandler 的作用: QueryRunner 的 query 方法的返回值最终取决于 query 方法的 ResultHandler 参数的 hanlde 方法的返回值。

2. BeanListHandler: 把结果集转为一个 Bean 的 List, 并返回.。Bean的类型在创建 BeanListHanlder对象时以 Class对象的方式传入，可以适应列的别名来映射 JavaBean 的属性 名:  String sql = "SELECT id, name customerName, email, birth " + "FROM customers WHERE id = ?"; BeanListHandler(Class<T> type)。

3. BeanHandler: 把结果集转为一个 Bean,并返回.。Bean的类型在创建BeanHandler 对象时以 Class 对象的方式传入 BeanHandler(Class<T> type)。

4. MapHandler: 把结果集转为一个 Map 对象, 并返回。若结果集中有多条记录, 仅返回 第一条记录对应的Map对象.。Map的键: 列名(而非列的别名), 值: 列的值。

5. MapListHandler: 把结果集转为一个 Map 对象的集合, 并返回.。Map的键: 列名(而非列的别名), 值: 列的值。

6. ScalarHandler: 可以返回指定列的一个值或返回一个统计函数的值，比如count(1)。

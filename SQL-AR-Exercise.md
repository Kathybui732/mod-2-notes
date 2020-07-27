#SQL and ActiveRecord Workshop

## Instructions

Choose one of the following problem sets to work on. Group up with students who are working on the same problem set.

With your group, work on the problem set. Try to whiteboard the problem first, then check your solution using rails dbconsole or rails c.

### Problem Set 1
As a merchant admin When I visit my dashboard, I see an area with statistics:

1. top 5 items I have sold by quantity, and the quantity of each that I’ve sold. Only items on “shipped” orders should be considered sold.
  ```
  ```
1. top 3 states where my items were shipped, and their quantities.
1. top 3 city/state where my items were shipped, and their quantities (Springfield, MI should not be grouped with Springfield, CO)
1. List of all of my items that have an average rating of 4 or greater that were never ordered by one of my employees.
1. top 3 users who have spent the most money on my items, and the total amount they’ve spent.

### Problem Set 2
As any kind of user on the system When I visit the items index page (“/items”) I see an area with statistics:

1. The 5 most expensive items.
```SELECT * FROM ITEMS ORDER BY price DESC LIMIT 5;
```
```Item.order(price: :desc).limit(5)
```
1. The top 5 merchants by count of items.
```select merchants.name, sum(items.inventory) as items_inventory from merchants join items on merchants.id = items.merchant_id group by merchants.id order by items_inventory desc;

This is based on inventory...Next query is more of what this is asking for...
```
```SELECT merchants.name FROM merchants JOIN items ON merchants.id = items.merchant_id GROUP BY merchants.id ORDER BY count(items) DESC LIMIT 5;
```
```Merchant.joins(:items).group(:id).order('count(items) desc').limit(5)

OR

Merchant.select('merchants.*, count(items) as item_count').joins(:items).group(:id).order('item_count desc').limit(5)
(This would return objects that have access to a method called #item_count that you can call to access how many items they actually have)
```
1. The 5 best selling items. This is determined by the total revenue the item has generated. Revenue should only be counted for “shipped” orders.
```SELECT items.name, sum(items.price * item_orders.quantity) AS revenue FROM items JOIN item_orders on items.id = item_orders.item_id JOIN orders ON orders.id = item_orders.order_id WHERE orders.status = 4 GROUP BY items.id ORDER BY revenue DESC LIMIT 5;
```
```Item.joins(:orders).group(:id).where('orders.status = ?', 0).order('sum(item_orders.price * item_orders.quantity) DESC').limit(5)
```
1. The names of the 5 users who have placed the most orders.
```SELECT users.name, count(orders) FROM users JOIN orders ON users.id = orders.user_id GROUP BY users.id ORDER BY count DESC;
```
```User.joins(:orders).group(:id).order('count(orders) desc').limit(5)

OR

User.select('users.*, count(orders)').joins(:orders).group(:id).order('count(orders) desc').limit(5)
```
1. The top 5 merchants by number of items sold.

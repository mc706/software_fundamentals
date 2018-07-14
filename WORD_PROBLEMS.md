# Software Fundamentals Practice

The following are example requirements lists different projects. For each, create a console application that executes and produces results inline with the requirements.

### Problem 1

Write a program that defines a number of classes for shapes. All classes should share a few methods:

* `GetArea()`
* `GetPerimeter()`
* `GetSides()`

Define the classes so they use the programming concepts of inheirtance and polymorphism. Define the following classes:

* Rectangle
* Square
* RightTriangle*

\*For RightTriangle, define a method `GetHypotenuse()` that gives the length of the third side. The formula for the `GetHypotenuse()` method goes is as follows:
```
private double GetHypotenuse()
{
      return Math.Sqrt(length * length + width * width);
}
```
This is based off of the Pythagorean Theorem `a^2 + b^2 = c^2`.  

The formulas for the rest of the above methods go as follows:

<table>
<thead>
<tr>
<th>Shape</th>
<th>Area</th>
<th>Perimeter</th>
</tr>
</thead>
<tbody>
<tr>
<td>Rectangle</td>
<td>length * width</td>
<td>length * 2 + width * 2</td>
</tr>
<tr>
<td>Square</td>
<td>length * length</td>
<td>length * 4</td>
</tr>
<tr>
<td>RightTriangle</td>
<td>(length * width) / 2</td>
<td>length + width + GetHypotenuse</td>
</tr>
</tbody>
</table>

Once you have defined these, define and run the following program in the same namespace.

```
static void Main(string[] args)
{
      ///this is a comment
      ///square Operations
      Square sqre = new Square(10);
      Console.WriteLine("The area of the square is {0}, the perimeter is {1}", sqre.GetArea(), sqre.GetPerimeter());

      ///rectangle operations
      Rectangle rect = new Rectangle(5, 11);
      Console.WriteLine("The area of the rectangle is {0}, the perimeter is {1}", rect.GetArea(), rect.GetPerimeter())

       ///right triangle operations
       RightTriangle rtri = new RightTriangle(3, 4);
       Console.WriteLine("The area of the triangle is {0}, the perimeter is {1}", rtri.GetArea(), rtri.GetPerimeter());
}
```

---

### Problem 2
Write a program that defines two classes, `Item` and `Cart`. 

Class `Item` should have the following properties:

* `Name`
* `Price`

Class `Cart` should have take a list of Items in its `constructor` and define a few methods:

* `GetPriceSum()` which should sum the prices of the items in the cart
* `CalculateDiscount()` which should calculate and return how much off you get based on the table below
* `CalculateTax()` should return a number + 6%
* `GetCheckoutPrice()` should return the outcome of `CalculateTax(GetPriceSum() - CalculateDiscount())`

Discount Table
<table>
<thead>
<tr>
<th>Total Price</th><th>Eligible Discount</th>
</tr>
</thead>
<tbody>
<tr>
<td>>$10</td><td>5% off</td>
</tr>
<tr>
<td>>$50</td><td>10% off</td>
</tr>
<tr>
<td>>$100</td><td>15% off</td>
</tr>
</tbody>
</table>

Once you are finished defining the `Item` and the `Cart` classes, run the following program.

```
static void Main(string[] args)
{
     Item apple = new Item("Apple", 3.00);
     Item banana = new Item("Banana", 5.00);
     Item steak = new Item("Steak", 24.00);
     Item chicken = new Item("Chicken", 15.00);

     Item[] shopping_cart = [apple, apple, banana, steak, steak, chicken];
     Cart cart = new Cart(shopping_cart);
     Console.WriteLine("The checkout price of this cart is {0}", cart.GetCheckoutPrice());
}
```

### Problem 3
Design a database according to the following requirements. Make sure that your data structures are fully normalized.

The requirements are you are building a social network. 

* `Users` have a first_name, last_name, username.
* `Users` can have many `Posts`
* `Posts` have a user, content, and a timestamp
* `Posts` have many `Comments`
* `Comments` have a user, content, and a timestamp

Draw a Entity Relationship Diagram (ERD) to describe how you would build the database for this social network.

### Problem 4
Create a console based application that implements FizzBuzz. your console application should take as an argument the number of to count up to. If a argument is not provided, it should default to 100.

FizzBuzz is defined as the following:

* Output the Numbers from 1 to N
* If the number is evenly divisble by 3, instead of the number, output "Fizz"
* If the number is evenly divisible by 5, instead of the number output "Buzz"
* IF the number is both divisible by 3 and 5, instead output "FizzBuzz"

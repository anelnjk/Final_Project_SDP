    This project represents Observer.Observer.Bakery application, which customer can use to make an order.
    Observer.Observer.Bakery has cakes and cupcakes in asertment, also there are twp tastes of desserts: vanilla and chocolate.
    Observer.Observer.Customer can decorate desserts with berry, candy or both of them.
    Observer.Observer.Customer can can pay online in advance, and is able to inform if he/she will get order by themselves or send a car.
    Observer.Observer.Bakery offers customer subscription to get notifications about special offers.

Patterns that were used in this project:
1) Bridge
2) Decorator
3) Facade
4) Observer.Observer
5) Strategy
6) Factory

Bridge pattern is applied as following:
Observer.Observer.Bakery has two different types of bakings: cakes and cupcakes; has two tastes: vanilla and chocolate.
Observer.Observer.Customer can combine them and create dessert that he/she wants.
Classes that were used: Cake.java, Cupcake.java, VanillaTaste.java, ChocolateTaste.java, abstract class Dessert.java,
interface DessertTastes.java.

Decorator pattern is applied as following:
Observer.Observer.Bakery offers customers to decorate dessert either with berries, candies or both. Price of the dessert changes
according to these decorations.
Classes that were used: Bridge.Cake.java, Bridge.Cupcake.java, ExtraBerry.java, ExtraCandy.java, abstract class DessertDecorator
and interface DessertInterface.java.

Facade pattern is applied as following:
FacadeDessert simplifies our main class during creation of final order, because according to choice of customer
to decorate dessert or not we create two different instances of desserts: Bridge.Dessert object or Decorator.DessertDecorator object.
In FacadeDessert.java we have all types of both classes and according to the choice of customer FacadeDessert.java
creates and returns us particular object.

Observer pattern is applied as following:
After making an order customer is offered to get subscription to get messages about all the new special offers
of Bakery. Also, if customer is subscriber he/she can unsubscribe and not get any notification further.
Classes that were used: Customer.java, Bakery.java, interfaces Subject.java, Observer.java.

Strategy pattern is applied as following:
After making an order customer gets a choice of payment either by credit card or cash. According to customer's
decision, there is a bill with note of payment method. Moreover, customer can have bonus after credit card payment
method only. There is an interface Payment.java which is implemented by PaymentByCreditCard.java and PaymentByCash.java,
where payment details of each method is written. PaymentStrategy.java will determine which payment method is being used
at runtime and will output final order price and bonus(credit card payment method). To simplify Main.java
payment decision is passed to createOrderCupcake(int paymentDecision) and createOrderCake(int paymentDecision)
in FacadeDessert.java.

Factory pattern is applied as following:
In the end of making an order customer choose a type of order (Tax or Pickup). After that it goes to our DeliveryFactory's
object and calls getDelivery method and returns delivery type according to our decision. For that purpose, we defined
interface of Delivery type and also created Factory class for delivery type where we get our result.
Classes and interfaces that were used: TaxDelivery.java, PickupDelivery.java, IDelivery.java, DeliveryFactory.java
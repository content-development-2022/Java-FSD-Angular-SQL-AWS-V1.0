Constructor Chaining

In constructor chain, a constructor is called from another constructor in the same class this process is known as **constructor chaining.** It occurs through inheritance. When we create an instance of a derived class, all the constructors of the inherited class (base class) are first invoked, after that the constructor of the calling class (derived class) is invoked.

We can achieve constructor chaining in two ways:

-   **Within the same class:** If the constructors belong to the same class, we use **this**
-   **From the base class:** If the constructor belongs to different classes (parent and child classes), we use the **super** keyword to call the constructor from the base class.

Remember that changing the order of the constructor does not affect the output.

![](media/chain-constructor.png)

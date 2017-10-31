# aspectj-generics-issue
Hunting down potentially AspectJ issue with interfaces and generics.  To reproduce execute:

    mvn clean compile 


Issue at hand is that class AlreadyImplementsA does indeed have a method that implements interface A, but the AJC compiler incorrectly deems it does not.  

The cause of the issue I believe comes down to the fact a generic \<I> is being used with an interface (java.util.List) as the argument to the lone interface method.  The generics as the return type don't seem to make a difference.  

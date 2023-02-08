# Reading-Notes Operators and Loops

Im not going to lie, loops and operators threw me for a loop... Pun intended! Its definitely something I will need wo work on a lot more in 201 and get way more comfortable with. 
. 
The equality and relational operators determine if one operand is greater than, less than, equal to, or not equal to another operand. The majority of these operators will probably look familiar to you as well. Keep in mind that you must use "==", not "=", when testing if two primitive values are equal.THe Following is a function loop from Oracle who invented the JavaScript Language.

==      equal to
!=      not equal to
>       greater than
>=      greater than or equal to
<       less than
<=      less than or equal to
The following program, ComparisonDemo, tests the comparison operators:


class ComparisonDemo {

    public static void main(String[] args){
        int value1 = 1;
        int value2 = 2;
        if(value1 == value2)
            System.out.println("value1 == value2");
        if(value1 != value2)
            System.out.println("value1 != value2");
        if(value1 > value2)
            System.out.println("value1 > value2");
        if(value1 < value2)
            System.out.println("value1 < value2");
        if(value1 <= value2)
            System.out.println("value1 <= value2");
    }
}
Output:

value1 != value2
value1 <  value2
value1 <= value2

[HOME](../README.md)
Download Link: https://assignmentchef.com/product/solved-cse225l-lab-06-stack-array-based
<br>
In today’s lab we will design and implement the Stack ADT using array.

<table width="0">

 <tbody>

  <tr>

   <td width="313"><strong><u>stacktype.h</u></strong><strong> </strong>#ifndef STACKTYPE_H_INCLUDED#define STACKTYPE_H_INCLUDED const int MAX_ITEMS = 5; class FullStack// Exception class thrown// by Push when stack is full.{};class EmptyStack// Exception class thrown// by Pop and Top when stack is emtpy.{};template &lt;class ItemType&gt; class StackType{     public:StackType();         bool IsFull();         bool IsEmpty();         void Push(ItemType);         void Pop();         ItemType Top();     private:int top;ItemType  items[MAX_ITEMS];}; #endif // STACKTYPE_H_INCLUDED  </td>

   <td width="399"><strong><u>stacktype.cpp</u></strong><strong> </strong>#include “StackType.h” template &lt;class ItemType&gt;StackType&lt;ItemType&gt;::StackType(){top = -1;}template &lt;class ItemType&gt;bool StackType&lt;ItemType&gt;::IsEmpty(){return (top == -1);}template &lt;class ItemType&gt;bool StackType&lt;ItemType&gt;::IsFull(){return (top ==  MAX_ITEMS-1);}template &lt;class ItemType&gt;void StackType&lt;ItemType&gt;::Push(ItemType newItem){if( IsFull() ) throw FullStack();     top++;items[top] = newItem;} template &lt;class ItemType&gt; void StackType&lt;ItemType&gt;::Pop(){if( IsEmpty() ) throw EmptyStack();     top–;}template &lt;class ItemType&gt;ItemType StackType&lt;ItemType&gt;::Top(){if (IsEmpty()) throw EmptyStack();     return items[top];}</td>

  </tr>

 </tbody>

</table>







Generate the <strong>driver file (main.cpp) </strong>where you perform the following tasks. Note that you cannot make any change to the header file or the source file.

<table width="0">

 <tbody>

  <tr>

   <td width="422"><strong>Operation to Be Tested and Description of Action </strong></td>

   <td width="118"><strong>Input Values </strong></td>

   <td width="163"><strong>Expected Output </strong></td>

  </tr>

  <tr>

   <td width="422">         •    Create a stack of integers</td>

   <td width="118"> </td>

   <td width="163"> </td>

  </tr>

  <tr>

   <td width="422">         •    Check if the stack is empty</td>

   <td width="118"> </td>

   <td width="163">Stack is Empty</td>

  </tr>

  <tr>

   <td width="422">         •     Push four  items</td>

   <td width="118">5  7  4  2</td>

   <td width="163"> </td>

  </tr>

  <tr>

   <td width="422">         •    Check if the stack is empty</td>

   <td width="118"> </td>

   <td width="163">Stack is not Empty</td>

  </tr>

  <tr>

   <td width="422">         •    Check if the stack is full</td>

   <td width="118"> </td>

   <td width="163">Stack is not full</td>

  </tr>

  <tr>

   <td width="422">•     Print the values in the stack (in the order the values are given as input)</td>

   <td width="118"> </td>

   <td width="163">5  7  4  2</td>

  </tr>

  <tr>

   <td width="422">         •    Push another item</td>

   <td width="118">3</td>

   <td width="163"> </td>

  </tr>

  <tr>

   <td width="422">         •    Print the values in the stack</td>

   <td width="118"> </td>

   <td width="163">5  7  4  2  3</td>

  </tr>

  <tr>

   <td width="422">         •    Check if the stack is full</td>

   <td width="118"> </td>

   <td width="163">Stack is full</td>

  </tr>

  <tr>

   <td width="422">         •     Pop two items</td>

   <td width="118"> </td>

   <td width="163"> </td>

  </tr>

  <tr>

   <td width="422">         •     Print top item</td>

   <td width="118"> </td>

   <td width="163">4</td>

  </tr>

  <tr>

   <td rowspan="4" width="422">•     Take strings of parentheses from the user as input and use a stack to check if the string of parentheses is balanced or not</td>

   <td width="118">()</td>

   <td width="163">Balanced</td>

  </tr>

  <tr>

   <td width="118">(())()(()())()</td>

   <td width="163">       Balanced</td>

  </tr>

  <tr>

   <td width="118">(())()((()</td>

   <td width="163">Not balanced</td>

  </tr>

  <tr>

   <td width="118">(())))((()</td>

   <td width="163">Not balanced</td>

  </tr>

 </tbody>

</table>



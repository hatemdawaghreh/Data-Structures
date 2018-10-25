
//  Created by Hatem Dawaghreh on 2018-10-24.
//  Copyright © 2018 Hatem Dawaghreh. All rights reserved.
//

#include <stdio.h>
#include <stdlib.h>

//define Node Structure
struct Node{
    int data;                       //define the data that each node will hold as an integer value
    struct Node* next;              //define the pointer that the node will point to, which will be the next integer.
};


//define printList, function that traverses linked list and prints each node value
void printList(struct Node* n)
{
    while (n != NULL) {
        printf(" %d ", n->data);
        n = n->next;
    }
}


//Push function: this function will add (push) a node to the beginning of a linked list
//Insert pointer to the head of the linked list and desired data value into the function
void push(struct Node** head_ref, int new_data)
{
    struct Node* new_Node = (struct Node*)malloc(sizeof(struct Node));          //creating Node
    
    new_Node->data = new_data;      //assign Node to have new value defined in function call
    new_Node->next = *(head_ref);   //in this line, we are making the new_Node point to the address of the first node in the linked list
    *(head_ref) = new_Node;         //now, we are getting the head reference to be the address of the new_Node, making it the first node in the list
    

}


//insertAfter function: this function will insert a desired node after a specific node, called prev_node (previous node)
void insertAfter(struct Node* prev_node, int new_data)
{
    struct Node* new_Node = (struct Node*)malloc(sizeof(struct Node));
    
    if(prev_node == NULL)       //check if previous node has null value, which shouldn't happen.
    {
        printf("ERROR");
        return;
    }
    
    new_Node->data = new_data;              //assign Node to have new value defined in function call
    new_Node->next = prev_node->next;       //we are getting the new node to point to what the node before it is pointing to, so that maintain the structure of the list.
    prev_node->next = new_Node;             //assign previous node to point to the new node
    
}

//insertLast function: this function inserts node at the end of the linked list. We will traverse the entire list to find the last value, then add the node after that.
void insertLast(struct Node** head_ref, int new_data)
{
    struct Node* new_Node = (struct Node*)malloc(sizeof(struct Node));
    struct Node *last= *head_ref;       //this might be clear right now, but it will become clear in the while() statement below
    
    new_Node->data = new_data;
    new_Node->next = NULL;              //last node of a list points to a NULL value, indicating list is complete. This is ensuring this property is maintained.
    
    if(*head_ref == NULL)               //this is essentially seeing if this list is empty, and (if true) consequently making the new node the head.
    {
        *head_ref = new_Node;
        return;
    }
    
    while(last->next != NULL)           //we use this while statemement to traverse the entire list and find the last node of the linked list.
    {
        last = last->next;              //if the node we are right now is not the last one in the list, move on to the next one.
    }
    
    last->next = new_Node;              //when we reach the last node, make it point to new_Node instead of a null value, making new_Node the last node in the list.
    return;
    
}


//creating Linked List that is [1] -> [2] -> [3]

int main()
{
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;
    
    
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));
    
    
    head->data = 1;
    head->next = second;
    
    second->data = 2;
    second->next = third;

    third->data = 3;
    third->next = NULL;
    
    return 0;
}

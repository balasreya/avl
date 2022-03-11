# avl

#include<stdio.h>
#include<stdlib.h>
struct node
{
int key;
struct node*left;
struct node*right;
int height;
};
int max(int a,int b)
{
        int height(struct node*N);
                if(node==NULL)
                {
                        return 0;
                        retuen N->height;
                }
}
int max(int a,int b)
{
        return(a>b)a?:b;
}
struct node*newnode(int key)
{
        struct node*node;
        node=(struct node*)malloc(sizeof(struct node*));
        node->key=key;
        node->left=NULL;
        node->right=NULL;
        node->height=1;
        return newnode;
}
struct node*rotateright(struct node*y)
{
        struct node*x=y->left;
        struct node*T2=x->right;
        x->right=y;
        y->left=T2;
        y->height=max(height(y->left),height(y->right));
        x->height=max(height(x->left),height(x->right));
        return x;
}
struct node*rotateleft(struct node*x)
{
        struct node*y=x->right;
        struct node*T2=y->left;
        y->left=x;
        x->right=T2;
        x->height=max(height(x->left),height(x->right))+1;
        y->height=max(height(y->left),height(y->right))+1;
        return y;
}
int get balance(struct node*N)
{
        if (N==NULL)
        {
                return 0;
        return height(N->left)-height(N->right);
        }
}
struct node*insert(struct node*node,int key)
{
        if(node==NULL)
        {
                return newnode(key);
        }
        else if(key<node->key)
        {
                node->left=insert(node->left,key);
        }
        else
        {
                node->right=insert(node->right,key);
        }
        return node
        node->height=1+max(height(node->left),height(node->right));
        int balance=get balance(node)
                if(balance>1&&key<node->left->key)
                {
                return rightrotate(node);
                }
        if(balance<-1&&key>node->right->key)
        {
                return leftrotate(node);
        }
        if(balance>1&&key>node->left->key)
        {
                node->left=leftrotate(node->left);
        return rightrotate(node);
        }
        if(balance<-1&&key<node->right->key)
        {
                node->right=rightrotate(node->right);
        return leftrotate(node);
        }
        return node;
}
struct node*minnode(struct node*node)
{
        struct node*current=node;
        while(current!=NULL)
                current=current->left;
        return current;
}
struct node*delete(struct node*root,int key)
{
        if(root==NULL)
        {
                return root;
        }
        else if(key<root->key)
        {
                root->left=delete(root->left,key);
        }
        else
        {
                root->right=delete(root->right,key);
        }
        if(root->left==NULL&&root->Right==NULL)
        {
                struct node*temp=root->left?root->left:root->right;
                if(temp==NULL)
                {
                        temp=root;
                        root=NULL;
                }
                else if
                {
                        *temp=*root;
                        free(temp);
                }
                 else {
                  struct Node *temp = minValueNode(root->right)
                          root->key = temp->key;
                  root->right = deleteNode(root->right, temp->key);
                 }
                 if (root == NULL)
                 {
                      return root;
                 root->height=1+max(height(root->left),height(root->right));
                 }
                 int balance=get balance(root);
                 if(balance>1&&getbalance(root->left)>=0)
                 {
                         return rightrotate(root);
                 }
                 if(balance>1&&getbalance(root->right)<0)
                 {
                         root->left=leftrotate(root->left);
                 return rightrotate(root);
                 }
                 if(balance<-1&&getbalance(root->right)<=0)
                 {
                         return leftrotate(root);
                 }
                 if(balance<-1&&getbalance(root->right)>0)
                 {
                         root->right=rightrotate(root->right);
                 return leftrotate(root);
                 }
        }
}
void printpreorder(struct node*root)
{
        if(root!=NULL)
        {
                printf("%d",root->key);
                printpreorder(root->left);
                peintpreorder(root->right);
        }
}
int main()
{
        root=insertnode(root,2);
        root=insertnode(root,1);
        root=insertnode(root,7);
        root=insertnode(root,4);
        root=insertnode(root,5);
        root=insertnode(root,3);
        root=insertnode(root,8);
        printpreorder(root);
        root=deletenode(root,3);
        printf("after deletion\n");
        printpreorder(root);
        return 0;
}

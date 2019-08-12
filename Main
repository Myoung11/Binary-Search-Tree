 /* Assisted by and Assisted line numbers: Dr.Su lines 50-77, 80-102, 104-113, 130, 161, 175-210
 
 * Matthew Young
 
 *This program will read through a txt file and search, count, and sort the words (Min 3 letters).
 
 */







#include <iostream>
#include <cstring>
#include <string>
#include <fstream>
#include <iomanip>

using namespace std; 


//Data stored in the node type

struct WordCount

{
    
    string word;
    
    int count;
    
};



//Node type:

struct TreeNode

{
    
    WordCount info;
    
    TreeNode * left;
    
    TreeNode * right;
    
};


class binNodes{ // Define a class to hold members and functions of the Binary Search Trees
    
    public:
    
        class TreeNode{
        
            public:
        
                TreeNode *left;
        
                TreeNode *right;
        
                int count;
        
                typedef string dataName;
        
                dataName info;
        
                TreeNode(dataName new_info){
                    info = new_info;
                    left = NULL;
                    right = NULL;
                };
        };
    
        void Insert(TreeNode*& root, string info);
    
        void PrintTree(TreeNode* root , ofstream& outFile);
    
        TreeNode *root;
    
        ~binNodes(){
        
            delete root;
        };
    
        typedef string dataName;
    
        binNodes(dataName root_info){
        
        root = new TreeNode(root_info);
        
    };
    
};


// Two function's prototype

// Increments the frequency count if the string is in the tree

// or inserts the string if it is not there.

void binNodes::Insert(TreeNode*& root, string info){ // Member function of the class binNodes to Insert words and trees
    
    if (root == NULL){
        
        root = new TreeNode(info);
    
        root->left = NULL;
        
        root->right = NULL;
        
        return;
}
    
    if (info < root->info){
        Insert(root->left, info);
    }
    
    if(info > root-> info){
        Insert(root->right, info); 
    }
    
    if(info == root->info){
        root->count++;
    }
}


    

// Prints the words in the tree and their frequency counts.

void binNodes::PrintTree(TreeNode* root , ofstream& outFile){ // Member function of the class binNodes to Print the trees
    
    if(root != NULL){
        PrintTree(root->left, outFile);
        
        outFile << root->info << " " << root->count << endl;
        
        PrintTree(root->right, outFile);
    }
    
    
}


int main(){
    

    binNodes trees("");
    
    string words;
    
    ifstream inFile;
    
    ofstream outFile;
    
    string infilename, outfilename;
    
    cout << "Please type the text file name: ";
    
    cin >> infilename;
    
    inFile.open(infilename.c_str());  // Open the file
    
    if (!inFile.is_open()){           // Check if the file exists
        cout << "File not found! " << endl;
        return 1;
    }
    
    cout << "Please give the output text file name: ";
    
    cin >> outfilename;
    
    outFile.open(outfilename.c_str());      // Open the file
    
    if (!outFile.is_open()){                // Check if the file exists
        cout << "File not found! " << endl;
        return 1;
    }
    
    while(inFile){                       // Loop to read through the txt file.
        inFile >> words;
        trees.Insert(trees.root, words); // Put the fle into the Insert Functoin.
    }
    
    trees.PrintTree(trees.root, outFile); // Put the file into the PrintTree function.
    
    cout << "You are done! You can open the file " << outfilename << " to check." << endl;
    
    inFile.close();
    outFile.close();
    
    return 0;
}

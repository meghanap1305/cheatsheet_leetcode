Here is a list of important topics or algorithms from arrays 
# Pointer arithmetic 
-> How these operations alter the memory address of the pointer refernce rather than value stored at the pointer
# Passing 2D arrays to functions 
-> Columnsize must be mentioned 
possible ways :
void printarr(int arr[][cols],rows)
void printarr(int row ,int col, int arr[row][col])
void printarr(int *arr ,int row,int col)
# Manipulating Multi xdimensional arrays without out-of-bounds

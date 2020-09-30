# Reshape-the-matrix

class Solution {
    public int[][] matrixReshape(int[][] nums, int r, int c) {
        
        //if the size of original array is not equal to output array return original array
        // row size= nums.length column size = nums[0].length
        if( (nums.length * nums[0].length)  != (r*c))//if size of original Matrix is not equal to reshaped Matrix then return original matrix.
        {
            return nums;
        }
        
        
        int[][] output = new int[r][c];
        int rowCount=0;
        int columnCount=0;
        
        for(int i=0;i<nums.length;i++) //for loop for traversing  row
        {
            
            for(int j=0;j<nums[0].length;j++)//for loop for traversing column
            {
                //first populate all column values when it reaches limit increment rows
                output[rowCount][columnCount] = nums[i][j];
                  columnCount++;
                if(columnCount == c)
                {
                    columnCount=0;
                    rowCount++;
                }
              
                 
            }
        }
        
        return output;
    }
}

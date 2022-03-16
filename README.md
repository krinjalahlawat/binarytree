# binarytree
zigzag question binary tree
 import java.util.Stack;
public class Solution {

	public static void printZigZag(BinaryTreeNode<Integer> root){

		/* Your class should be named Solution
		 * Don't write main().
		 * Don't read input, it is passed as function argument.
		 * Return output and don't print it.
	 	 * Taking input and printing output is handled automatically.
        */
        
		Stack<BinaryTreeNode<Integer>> stack1  = new Stack<>();
		Stack<BinaryTreeNode<Integer>> stack2 = new Stack<>();
		
		stack1.push(root);
		
		while( !(stack1.isEmpty() && stack2.isEmpty()) ) {
			while(!stack1.isEmpty()) {
				BinaryTreeNode<Integer> frontNode = stack1.pop();
				System.out.print(frontNode.data+" ");
				if(frontNode.left!=null) {
					stack2.push(frontNode.left);
				}
				if(frontNode.right!=null) {
					stack2.push(frontNode.right);
				}
			}
			System.out.println();
			while(!stack2.isEmpty()) {
				BinaryTreeNode<Integer> frontNode = stack2.pop();
				System.out.print(frontNode.data+" ");
				if(frontNode.right!=null) {
					stack1.push(frontNode.right);
				}
				if(frontNode.left!=null) {
					stack1.push(frontNode.left);
				}
			}
			System.out.println();
		}
	}

}

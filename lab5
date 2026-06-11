class Node:
    def __init__(self, value, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def build_expression_tree(tokens):
    stack = []
    for token in tokens:
        if token in ('+', '-', '*', '/'):
            right = stack.pop()
            left = stack.pop()
            stack.append(Node(token, left, right))
        else:
            stack.append(Node(int(token)))
    return stack[0]

def evaluate(root):
    if not root.left and not root.right:
        return root.value

    left_val = evaluate(root.left)
    right_val = evaluate(root.right)
    
    if root.value == '+': return left_val + right_val
    if root.value == '-': return left_val - right_val
    if root.value == '*': return left_val * right_val
    if root.value == '/': return left_val / right_val

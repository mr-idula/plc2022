# plc2022
Programming Language Concepts Fall 2022

Lexical Analyzer and Syntaz Analyzer. 
In the lexical analyzer class, I assigned each token (which included mathematical operations, variable assignments, characters, strings, natural literals, real literals) to a symbol or character. Based off the production rules I made, the methods (methods were chosen based off the starting character or symbol) in the syntax analyzer confirm if the statement is valid or not. 

Production Rules: 
S is the starting state. 
S -> <stmt> 
<stmt> —> <loop_stmt> ; | <block> ; | <ass_ign> ;| <if_stmt> ;| <var>; | <func_stmt> | <ass_ignbool> ; 
<block> —> ‘{‘ { <stmt> ‘;’ } ‘}’
<if_stmt> —> ‘$’’(‘ <bool_expr> ‘)’ <stmt> { ‘else’ <stmt> }
<loop_stmt> --> '@' '(' <bool_expr> ')' '{' <stmt> '}'
<bool_expr>  —> ‘(‘ <expr> {‘<' | ‘>’ |  ‘<==‘ | ‘>==‘ | '==' | '!=='| '!' | '&' | '|' } <expr>‘)’
<var>  —>  ('c' | 's' | 'b' | 'n' | 'r')  ‘ id ‘;’ <ass_ignbool> | <ass_ign> 
* note --> in variable declaration, the variable type is before the id 
but in assignment the id is before the variable type. Assignment of boolean
must begin with one *
<ass_ignbool> --> '*' id b '=' ('true'| 'false')
<ass_ign> —>  id ('c' | 's' | 'n' | 'r')  ‘=‘ <e> ';'
<func_stmt> --> '**' id '('  var ','  var ')' '{' <stmt> '}' ';' 
* note --> based off of the rules I have created, there are only 2 parameters allowed in each function declaration. 
<e> —> <t> { ( ‘/‘ | ‘%’ | ‘-‘ | '^') <t> }
<t> —> <f> { ( ‘*’ | ‘+’) <f> }
<f> —> ‘(‘ <e> ‘)’ | c | s | b | n | r | id  '(' '-''-'<e>')'

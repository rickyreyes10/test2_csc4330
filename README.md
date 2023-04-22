this repository contains the RDA python code (lexical analyzer and everything), The text file (.txt) that is the denotational semantics of the grammar, pdf file that contains screenshots of the lr parse table, and the text file (.txt) that contains over 20 valid tokens (25 to be exact) that is valid for the grammar and RDA python code


For the LR parse table... this the grammar I used:           

S' -> STMT
STMT -> IF_STMT | BLOCK | ASSIGN | DECLARE | WHILE_LOOP
STMT_LIST -> STMT ; | STMT ; STMT_LIST
WHILE_LOOP -> while ( BOOL_EXPR ) BLOCK
IF_STMT -> if ( BOOL_EXPR ) BLOCK | if ( BOOL_EXPR ) BLOCK else BLOCK
BLOCK -> { } | { STMT_LIST }
DECLARE -> DataType ID | DataType ID , DECLARE
ASSIGN -> ID = EXPR
EXPR -> TERM EXPR' | TERM
EXPR' -> + TERM | - TERM | ε
TERM -> FACT TERM' | FACT
TERM' -> * FACT | / FACT | % FACT | ε
FACT -> ID | INT_LIT | FLOAT_LIT | ( EXPR )
BOOL_EXPR -> BTERM BOOL_EXPR' | BTERM
BOOL_EXPR' -> > BTERM | < BTERM | >= BTERM | <= BTERM | ε
BTERM -> BAND BTERM' | BAND
BTERM' -> == BAND | != BAND | ε
BAND -> BOR BAND' | BOR
BAND' -> && BOR | ε
BOR -> EXPR BOR' | EXPR
BOR' -> || EXPR | ε

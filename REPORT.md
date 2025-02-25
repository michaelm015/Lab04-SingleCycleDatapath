## Section 1
### Bugs and Issues
I did not encounter any bugs are major issues. When I was failing tests my verilog exported with CPU memory DIG_RAMDualAccess_i5, but when I passed all the tests it changed to i7 which I thought was interesting.

## Section 2
### Hand Trace Program
and $t0 $t1 $t2 <br/>
addi $t3 $t4 123 <br/>
lw $t5, 135($t1) <br/>
sw $t3, 136($t1) <br/>
beq $t3, $zero, -10 <br/>


### Initial Conditions
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0 |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x00000000 |


### After "and $t0 $t1 $t2"
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0 |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x00000000 |


### After "addi $t3 $t4 123"
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0x7B |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x00000000 |


### After "lw $t5, 135($t1)"
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0x7B |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x00000000 |


### After "sw $t3, 136($t1)"
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0x7B |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x0000007B |


### After "beq $t3, $zero, -10"
| Register Name	| Register Address | Value |
|---------------|------------------|-------|
| $zero	| 0 |	0 |
| $t0 |	8 |	0 |
| $t1	| 9	| 0 |
| $t2	| 10 | 0 |
| $t3	| 11 | 0x7B |
| $t4	| 12 | 0 |
| $t5	| 13 | 0 |

| Address	| Value	|
|---------|-------|
| 135	| 0x00000000 |
| 136 | 0x0000007B |

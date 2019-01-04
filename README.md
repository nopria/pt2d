# pt2d
## Projective transformation matrix between two quadrangles on a 2D plane

A little aid to compute what's described in https://math.stackexchange.com/a/339033/412495

### Matrix A (or B)

![Matrix A or B.](https://github.com/nopria/pt2d/blob/master/AB.png)

The following is a [Maxima](http://maxima.sourceforge.net/) symbolic definition of matrix A (the format is meaningful enough to be and easily translatable to any other language format):

    matrix(
		[(x_1*(x_2*(y_4-y_3)+x_3*(y_2-y_4)+x_4*(y_3-y_2)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	-(x_2*(x_1*(y_4-y_3)+x_3*(y_1-y_4)+x_4*(y_3-y_1)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	(x_3*(x_1*(y_4-y_2)+x_2*(y_1-y_4)+x_4*(y_2-y_1)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1))],
		[(y_1*(x_2*(y_4-y_3)+x_3*(y_2-y_4)+x_4*(y_3-y_2)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	-(y_2*(x_1*(y_4-y_3)+x_3*(y_1-y_4)+x_4*(y_3-y_1)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	(y_3*(x_1*(y_4-y_2)+x_2*(y_1-y_4)+x_4*(y_2-y_1)))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1))],
		[(x_2*(y_4-y_3)+x_3*(y_2-y_4)+x_4*(y_3-y_2))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	-(x_1*(y_4-y_3)+x_3*(y_1-y_4)+x_4*(y_3-y_1))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1)),	(x_1*(y_4-y_2)+x_2*(y_1-y_4)+x_4*(y_2-y_1))/(x_1*(y_3-y_2)+x_2*(y_1-y_3)+x_3*(y_2-y_1))]
	)
  
### Inverse of A

![Inverse of matrix A.](https://github.com/nopria/pt2d/blob/master/inverse_of_A.png)

The following is a Maxima symbolic definition of the inverse of matrix A:

    matrix(
		[-(y_3-y_2)/(x_3*y_4-x_2*y_4-x_4*y_3+x_2*y_3+x_4*y_2-x_3*y_2),	(x_3-x_2)/(x_3*y_4-x_2*y_4-x_4*y_3+x_2*y_3+x_4*y_2-x_3*y_2),	(x_2*y_3-x_3*y_2)/(x_3*y_4-x_2*y_4-x_4*y_3+x_2*y_3+x_4*y_2-x_3*y_2)],
		[-(y_3-y_1)/(x_3*y_4-x_1*y_4-x_4*y_3+x_1*y_3+x_4*y_1-x_3*y_1),	(x_3-x_1)/(x_3*y_4-x_1*y_4-x_4*y_3+x_1*y_3+x_4*y_1-x_3*y_1),	(x_1*y_3-x_3*y_1)/(x_3*y_4-x_1*y_4-x_4*y_3+x_1*y_3+x_4*y_1-x_3*y_1)],
		[-(y_2-y_1)/(x_2*y_4-x_1*y_4-x_4*y_2+x_1*y_2+x_4*y_1-x_2*y_1),	(x_2-x_1)/(x_2*y_4-x_1*y_4-x_4*y_2+x_1*y_2+x_4*y_1-x_2*y_1),	(x_1*y_2-x_2*y_1)/(x_2*y_4-x_1*y_4-x_4*y_2+x_1*y_2+x_4*y_1-x_2*y_1)]
	)

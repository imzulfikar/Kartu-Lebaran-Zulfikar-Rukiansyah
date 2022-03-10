<?php

$N = 3;


function rotateMatrix(&$mat)
{
	global $N;
	

	for ($x = 0; $x < $N / 2; $x++)
	{
	
		for ($y = $x;
			$y < $N - $x - 1; $y++)
		{

			$temp = $mat[$x][$y];

	
			$mat[$x][$y] = $mat[$y][$N - 1 - $x];

	
			$mat[$y][$N - 1 - $x] =
				$mat[$N - 1 - $x][$N - 1 - $y];


			$mat[$N - 1 - $x][$N - 1 - $y] =
						$mat[$N - 1 - $y][$x];

		
			$mat[$N - 1 - $y][$x] = $temp;
		}
	}
}


function displayMatrix(&$mat)
{
	global $N;
	for ($i = 0; $i < $N; $i++)
	{
		for ($j = 0; $j < $N; $j++)
			echo $mat[$i][$j] . " ";

		echo "\n";
	}
	echo "\n";
}

$mat = array(array(1, 2, 3, 4),
			array(5, 6, 7, 8),
			array(9, 10, 11, 12),
			array(13, 14, 15, 16));


rotateMatrix($mat);

displayMatrix($mat);


?>

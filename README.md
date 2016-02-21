# ProblemSet05JamesAndrus

	
	import edu.princeton.cs.algs4.Knuth;
	import edu.princeton.cs.algs4.Shell;
	
	//James Andrus
	//CSCI 223
	//2/21/16
	
	public class ShellSortWorstCase {
	
		public static void main(String[] args) {
			Comparable[] ints = new Comparable[100];
	
			// fill array of 100 integers with 1 to 100
			for (int i = 0; i < ints.length; i++) {
				ints[i] = i + 1;
			}
	
			int counter = 0;
			int average = 0;
			int maximum = 0;
			int minimum = 1000;
	
			// while loop to repeat experiment
			while (counter <= 100000) {
				// shuffle
				Knuth.shuffle(ints);
				// sort
				Shell.sort(ints);
				// get number of compares
				int compares = Shell.getCompares();
				// track average
				average += compares;
				// check for max
				if (compares > maximum)
					maximum = compares;
				// check for min
				if (compares < minimum)
					minimum = compares;
				// increment counter
				counter++;
	
			}
			System.out.println("Largest number of compares is " + maximum + ". \nThe average number of compares is "
					+ average / counter + ". \nThe smallest number of compares is " + minimum + ".");
		}
	
	}

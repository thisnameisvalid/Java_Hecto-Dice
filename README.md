class hecto_dice {
	public static void main(String[] args) {
		
		int diceroll;
		int[] rollcount = new int[50];
		float h_roll_counter = 0;
		float m_roll_counter = 0;
		float l_roll_counter = 0;
		
		System.out.println("This program rolls"
				+ " a 100 sided dice " + rollcount.length
				+ " times, and tells you \nhow well it did.\n");
		
		System.out.println("Between 1-33 is bad,"
				+ "\n34-66 is ok, and" 
				+"\n67-100 is a high roll.");
		
			for(int counter=0; counter<rollcount.length; counter++) {
					diceroll = (int)(Math.ceil(Math.random()*100));
					//roll dice 1-100 and store the integer value in diceroll
					
					System.out.println("\nThe dice has been rolled!");
					System.out.println(diceroll);
					//print the value in diceroll
					
					rollcount[counter] = diceroll;
					//fill up the rollcount array with values from diceroll
							
					if (rollcount[counter] > 66)
					{
						System.out.println("You rolled a " + rollcount[counter]
								+ ", you had a high roll! Nice!");
						h_roll_counter += 1;
							
						if (h_roll_counter > 1)
								System.out.println("You've had " 
								+ (int)h_roll_counter + " high rolls!");
						
					}
					
					else if (rollcount[counter] > 33)
					{
						System.out.println("You rolled a " + rollcount[counter]
								+ "...pretty average.");
						m_roll_counter += 1;
						if (m_roll_counter > 1)
							System.out.println("You've had " 
							+ (int)m_roll_counter + " <OK> rolls!");
						
							
					}
					
					else 
					{
						System.out.println("You rolled a " + rollcount[counter]
								+ "...not too good.");
						l_roll_counter += 1;
						
						if (l_roll_counter > 1)
							System.out.println("You've had " 
							+ (int)l_roll_counter + " bad rolls!");
						
					}	
					
			}
			
			System.out.println("\nSo, in total, out of " + rollcount.length
					+ " rolls, you had " 
					+ (int)l_roll_counter + " bad rolls,\n"
					+ (int)m_roll_counter
					+ " average rolls, and " 
					+ (int)h_roll_counter + " high rolls.\n");
			
			float l_roll_odds = 100 * (l_roll_counter / (float)rollcount.length);
			float m_roll_odds = 100 * (m_roll_counter / (float)rollcount.length);
			float h_roll_odds = 100 * (h_roll_counter / (float)rollcount.length);
			
			System.out.println("You had a bad roll " + 
					l_roll_odds + "% of the time,\na medium roll " +
					m_roll_odds + "% of the time, and \na high roll " +
					h_roll_odds + "% of the time.");

		}

	}

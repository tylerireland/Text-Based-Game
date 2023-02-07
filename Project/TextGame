import java.util.Date;
import java.util.Random;
import java.util.Scanner;
import java.util.concurrent.TimeUnit;



public class TextGame {

	static void Sleep(double time) {
		try {
		    TimeUnit.SECONDS.sleep((long) time);
		} catch (InterruptedException ie) {
		    Thread.currentThread().interrupt();
	    }
	}
	
	static boolean bossFight(int numEnemiesDefeated) {
		if(numEnemiesDefeated > 0 && numEnemiesDefeated % 5 == 0) {
			return true;
		}
		return false;
	}
	
	// Timer for experience orb
	public static boolean Timer(long startTime) {   
		long endTime = new Date().getTime();
		// 2 minute timer
		if(endTime-startTime < 120000) { 
			return true;
		} 
		
			return false;
	}
	
		

	
	public static void main(String[] args) {
	// System objects
		Scanner in = new Scanner(System.in);
		Random rand = new Random();
		boolean running = true;
		
	// ENEMY STATS
		
		// NORMIE STATS
		String[] enemies = {"Zombie","Ghost","Troll","Vampire","Skeleton","Joker"};
		int MinEnemyHealth = 50;
		int MaxEnemyHealth = 75;
		int MaxEnemyDamage = 50;
		int numEnemiesDefeated = 0;
		int timeEnemyAppeared = 6;
		double DropMulti = 1.00;
		
	   // BOSS STATS
		
		String[] bosses = {"Godzilla","Serpent King","Devil","Giant","King Kong"};
		int MinBossHealth = 150;
		int MaxBossHealth = 250;
		int MinBossDamage = 30;
		int MaxBossDamage = 70;
		int numBossesDefeated = 0;
		
	  // JOKER STATS 
		String[] suits = {"Clubs","Spades","Diamonds","Hearts"};
		int MinJokerDamage = 20;
		int MaxJokerDamage = 50;
		boolean JokerLives = false;
		int MaxHealthDropped = 5;
		
	// PLAYER STATS
		
		int MaxPlayerHealth = 100;
		int PlayerHealth = 100;
		int PlayerLives = 3;
		
		// MELEE STATS
		int MaxMeleeDamage = 40;
		int MinMeleeDamage = 10;
		
		// BOW STATS
		int MaxArrowDamage = 25;
		int MinArrowDamage = 10;
		int TotalArrows = 5;
		int ArrowDropRate = 20;
		
		// MAGIC
		boolean MagicUnlocked = false;
		boolean Frozen = false;
		int FrozenRounds = 3;
		int MaxFireDamage = 75;
		int MinFireDamage = 40;
		int numFireballs = 3;
		int MaxFreezeDamage = 25;
		int MinFreezeDamage = 5;
		int numIceballs = 2;
		
		
	// EXPERIENCE STATS
		
		int MinExpDrop = 5;
		int MaxExpDrop = 20;
		double BossMultiplier = 1.50;
		int MaxExp = 50; // increases as you level up
		int ExpRemaining = MaxExp;
		int PlayerLevel = 1;			
		int ExpMultiplier = 2;
		boolean ExpMulti = false;
		int ExpMultiChance = 5;
		long startTime = 0;
		int ExpCarry = 0;


		
		
	//POTION STATS
		
		// HEALTH POTION   --  Heals player
		
		int numHealthPotion = 3;
		int MinPotHeal = 20;
		int MaxPotHeal = (MaxPlayerHealth - 40);
		int HealthPotDrop = 40; // percentage
		
		// BUFF POTION	  --  Double damage for one battle
		
		int numBuffPotion = 1;
		int BuffPotDrop = 20;  //percentage
		int Buffer = 2;  //multiplier
		boolean Buffed = false;
		
		// WITCHES BREW  --  Always player to escape battle without taking damage
		
		int numWitchBrew = 1;
		
		// WEAKNESS POTION  --  Decreases enemy damge to half for one battle
		
		boolean Weakened = false;
		int numWeakPotion = 1;
		int WeakPotDrop = 20;
		double Weakening = 0.58;
		
		
		System.out.println("Welcome to the most interesting game that you'll ever play in your life.");
		Sleep(2);
		System.out.println("You are just a lonely warrior who goes for a stroll in the woods only to find"
				          + "\nthat there are monsters that try to kill you the whole time!\n");
		Sleep(2);
		System.out.println("How many monsters can you fend off before your doom?\n");
		Sleep(1);
		
		GAME:
		while(running) {
			
			String enemy = "";
			String JokersCard = "";
			int enemyHealth = 0;
			
			// checks if boss fight to create boss variables
			if(bossFight(numEnemiesDefeated)) {
				enemy = bosses[rand.nextInt(bosses.length)];
				enemyHealth = rand.nextInt(MaxBossHealth - MinBossHealth) + MinBossHealth;
				System.out.println("You sense a boss battle approaching...");
				Sleep(2);
				
			} else {
				enemy = enemies[rand.nextInt(enemies.length)];
				enemyHealth = rand.nextInt(MaxEnemyHealth - MinEnemyHealth) + MinEnemyHealth;
			}
			
			if(PlayerLevel < 2) {
				if(enemy.equals("Joker")) {
					enemy = "Jester";
				}
			}
			if(enemy.equals("Alien")) {
				System.out.println("An " + enemy + " has appeared!");
			} else {
				System.out.println("A " + enemy + " has appeared!");
			}
			
// JOKER BATTLE
			Sleep(1);
			
			if(enemy.equals("Joker")) {
				JokerLives = true;
				while(JokerLives) {
					JokersCard = suits[rand.nextInt(suits.length)];
					String cardChoice = "";
					String card = "";
					
					System.out.println("Your Health: " + PlayerHealth);
					Sleep(1);
					System.out.println("\nYou must choose the right suit to defeat him!");
					
					System.out.println("1. Clubs");
					System.out.println("2. Spades");
					System.out.println("3. Hearts");
					System.out.println("4. Diamonds");
					System.out.print(">>> ");
					
					cardChoice = in.nextLine();
					
					switch(cardChoice) {
					case "1":
						card = "Clubs";
						break;
					case "2":
						card = "Spades";
						break;
					case "3":
						card = "Hearts";
						break;
					case "4":
						card = "Diamonds";
						break;
					default:
							continue;
					}
					
					System.out.println("\nYour Card: " + card);
					Sleep(1);
					System.out.println("Joker's Card: " + JokersCard);
					Sleep(2);
		// CORRECT CARD
					if(card.equals(JokersCard)) {
						System.out.println("\nYou defeated the Joker!\n");
						JokerLives = false;
		// DROP HEALTH 
						int JokerPotDrop = rand.nextInt(MaxHealthDropped - 1) + 1;
						numHealthPotion+=JokerPotDrop;
						System.out.print("Health potions earned: " + JokerPotDrop);
		// DROP EXP
						int ExpDropped = (rand.nextInt(MaxExpDrop - MinExpDrop) + MinExpDrop)*ExpMultiplier;
						ExpRemaining-=ExpDropped;
						Sleep(1.5);
						System.out.println("\nYou earned " + ExpDropped + " XP\n");
						Sleep(1);
						// Player Level Up
						if(ExpRemaining <= 0) {
							ExpCarry = ExpRemaining;
							System.out.println("You leveled up!");
							Sleep(2.5);
							// set new xp level
							MaxExp*=(1+(PlayerLevel/3));
							ExpRemaining = MaxExp;
							ExpRemaining+= ExpCarry;
							// increase player stats
							PlayerLevel++;
							MaxPlayerHealth*=1.15;
							PlayerHealth = MaxPlayerHealth;
							MinMeleeDamage+=7;
							MaxMeleeDamage+=7;
							MinArrowDamage+=7;
							MaxArrowDamage+=7;
							// increase loot drop rate
							DropMulti+=(0.5/PlayerLevel);
							BossMultiplier+=(0.5/PlayerLevel);
							// After level, monsters get stronger
							MinBossDamage*=(1+(PlayerLevel/6));
							MaxBossDamage*=(1+(PlayerLevel/6));
							MaxEnemyDamage*=(1+(PlayerLevel/6));
							MinEnemyHealth*=(1+(PlayerLevel/6));
							MaxEnemyHealth*=(1+(PlayerLevel/6));
							MaxBossHealth*=(1+(PlayerLevel/5));
							MinBossHealth*=(1+(PlayerLevel/5));
							// increase Exp Drop
							MinExpDrop*=(1+(PlayerLevel/4));
							MaxExpDrop*=(1+(PlayerLevel/4));
							System.out.println("You are now player level "  + PlayerLevel + "\n");
						}
						
						System.out.println("Experience remaining until next level up: " + ExpRemaining + " XP\n");

						numEnemiesDefeated++;
						Sleep(rand.nextInt(timeEnemyAppeared) + 1);
						continue GAME;
		// WRONG CARD
					} else {
						System.out.println("\nYou picked the wrong card!\n");
						Sleep(1);
						int EnemyDamageDealt = rand.nextInt(MaxJokerDamage-MinJokerDamage) + MinJokerDamage;
						PlayerHealth -= EnemyDamageDealt;
						System.out.println("The " + enemy + " dealt " + EnemyDamageDealt + " HP to you");
		// YOU DIED
						if(PlayerHealth <= 0) {
							Sleep(1);
							System.out.println("\nYou were defeated!");
							Sleep(1);
							System.out.println("Bosses killed: " + numBossesDefeated);
							System.out.println("Total monsters killed: " + numEnemiesDefeated);
							running = false;
							continue GAME;
							
						}
					}
				}
			}
			
			
			
			while(enemyHealth > 0 & PlayerHealth > 0) {
				
				if(FrozenRounds == 0) {
					Frozen = false;
				}
				
				int PlayerDamageDealt = 0;
				int EnemyDamageDealt = 0;
				
				System.out.println("\nYour Health: " + PlayerHealth + " HP");
				System.out.println(enemy + "'s Health: " + enemyHealth + " HP");
				Sleep(1);
				System.out.println("\nWhat do you want to do?");
				System.out.println("1. Melee Attack");
				System.out.println("2. Arrow Attack (" + TotalArrows + ")");
				
				if(MagicUnlocked) {
					System.out.println("3. Use Magic");
					System.out.println("4. Use Potion");
					System.out.println("5. Run");
					System.out.print(">>> ");
				} else {
					System.out.println("3. Use Potion");
					System.out.println("4. Run");
					System.out.print(">>> ");
				}
				
				String choice = in.nextLine();
				
				if(!MagicUnlocked) {
					if(choice.equals("3")) {
						choice = "4";
					} else if(choice.equals("4")) {
						choice = "5";
					}
				}

			// If magic is unlocked, use if statement to increment choice before using switch //
				
				switch(choice) {
				
	//---------------------------------------------------------------------------------------------------------------------//
	// 	MELEE ATTACK 
					case "1":
				
						PlayerDamageDealt = rand.nextInt(MaxMeleeDamage-MinMeleeDamage) + MinMeleeDamage;
						EnemyDamageDealt = rand.nextInt(MaxEnemyDamage);
						
						// changes player damage if buff is used
						if(Buffed) {
							PlayerDamageDealt*=Buffer;
						}
						
						// changes damage if its a boss fight
						if(bossFight(numEnemiesDefeated)) {
							EnemyDamageDealt = rand.nextInt(MaxBossDamage - MinBossDamage) + MinBossDamage;
						}
						
						// changes monster damage if weakened
						if(Weakened) {
							EnemyDamageDealt*=Weakening;
						}
						
						enemyHealth -= PlayerDamageDealt;
						
						
						Sleep(1.5);
						System.out.println("\nYou dealt " + PlayerDamageDealt + " HP to the " + enemy);
						Sleep(1);	
						
						if(!Frozen) {
						
							if(enemyHealth > 0) {
								
								PlayerHealth -= EnemyDamageDealt;
								System.out.println("The " + enemy + " dealt " + EnemyDamageDealt + " HP to you");
								
							}
							
						} else if(Frozen) {
							
							FrozenRounds--;
							if(FrozenRounds == 0) {
								System.out.println("The " + enemy + " unfroze!");
							}
							
						}
						
						Sleep(1.5);
	
						break;
	//---------------------------------------------------------------------------------------------------------------------//
	// ARROW ATTACK
					case "2":
						if(TotalArrows > 0) {
							Sleep(1);
							PlayerDamageDealt = rand.nextInt(MaxArrowDamage-MinArrowDamage) + MinArrowDamage;
							TotalArrows--;
							
							 
							if(Buffed) {
								PlayerDamageDealt*=Buffer;
							}
							
							enemyHealth -= PlayerDamageDealt;
							System.out.println("\nYou dealt " + PlayerDamageDealt + " HP to the " + enemy);
							Sleep(1);						
							
							} else {
								System.out.println("No Arrows Left!");
							}
						
						break;
						
	//---------------------------------------------------------------------------------------------------------------------//
	  // MAGIC
					case "3":
						System.out.println("Select Magic:");
						System.out.println("1. Fireball (" + numFireballs + ")");
						System.out.println("2. iceball (" + numIceballs + ")");
						System.out.print(">>> ");

						String magChoice = in.nextLine();
						
				// FIREBALLS	
						if(magChoice.equals("1")) {
							if(numFireballs > 0) {
								Sleep(1);
								PlayerDamageDealt = rand.nextInt(MaxFireDamage-MinFireDamage) + MinFireDamage;
								numFireballs--;
								
								 
								if(Buffed) {
									PlayerDamageDealt*=Buffer;
								}
								
								enemyHealth -= PlayerDamageDealt;
								System.out.println("\nYou dealt " + PlayerDamageDealt + " HP to the " + enemy);
								Sleep(1);
								
							} else {
								System.out.println("\nNo fireballs left!\n");
							}
							
				// ICEBALLS
						} else if(magChoice.equals("2")) {
							if(numIceballs > 0) {
								Sleep(1);
								PlayerDamageDealt = rand.nextInt(MaxFreezeDamage-MinFreezeDamage) + MinFreezeDamage;
								numIceballs--;
								
								Frozen = true;
								FrozenRounds = 3;
								
								if(Buffed) {
									PlayerDamageDealt*=Buffer;
								}
								
								enemyHealth -= PlayerDamageDealt;
								System.out.println("\nYou dealt " + PlayerDamageDealt + " HP to the " + enemy);
								Sleep(1);
								
								System.out.println("The " + enemy + " has been temporarily frozen!");
								Sleep(1.5);
								
								
							} else {
								System.out.println("\nNo iceballs left!\n");
							}
							
						} else {
							break;
						}
						Sleep(1.5);
						break;
	//---------------------------------------------------------------------------------------------------------------------//
		// POTIONS
					case "4":
						System.out.println("Select Potion:");
						System.out.println("1. Health Potion (" + numHealthPotion + ")");
						System.out.println("2. Buff Potion (" + numBuffPotion + ")");
						System.out.println("3. Witches Brew (" + numWitchBrew + ")");
						System.out.println("4. Weakness Potion (" + numWeakPotion + ")");
						System.out.println("5. Go Back");
						System.out.print(">>> ");

						String Potchoice = in.nextLine();
						
				// Health Potion
						if(Potchoice.equals("1")) {
							
							if(numHealthPotion > 0) {
								
								int HealthGained = rand.nextInt(MaxPotHeal-MinPotHeal)+MinPotHeal;
								numHealthPotion--;
								
								PlayerHealth += HealthGained;
								
								System.out.println("You healed " + HealthGained + " HP");
								Sleep(1);
								
								if(PlayerHealth > 100) {
									PlayerHealth = MaxPlayerHealth;
								}
								
							} else {
								System.out.println("You have no potions left!");
							}
						
							
				// Buff Potion
						} else if(Potchoice.equals("2")) {
							
							if(numBuffPotion > 0) {
								
								numBuffPotion--;
								Buffed = true;
								
								System.out.println("You used a buff potion.");
								Sleep(1);
								System.out.println("Your damage will double for the remainder of the battle");
								
								
							} else {
								System.out.print("You have no buff potions left!\n");
							}
							
							
				// Witches Brew 	
						}else if (Potchoice.equals("3")) {
							
							if(numWitchBrew > 0) {
								numWitchBrew--;
								
								System.out.println("You used your witches brew and turned into an apple tree.");
								Sleep(1);
								
								System.out.println("The " + enemy + " has walked away!\n");
																
								Sleep(rand.nextInt(timeEnemyAppeared) + 1);
								continue GAME;
								
							} else {
								System.out.println("You have no more witches brew!");
							}
							
						} else if (Potchoice.contentEquals("4")) {
							
							if(numWeakPotion > 0) {
								
								numWeakPotion--;
								Weakened = true;
						
								System.out.println("You used a weakness potion!");
								Sleep(1);
								System.out.println("The " + enemy + " is weakened!");
								
							} else  {
								System.out.println("You have no weakness potions left!");
							}
						
						} else {
							break;
						}
				
						Sleep(1.5);
						break;
						
	//---------------------------------------------------------------------------------------------------------------------//
	   // RUN
					case "5":
						if(!bossFight(numEnemiesDefeated)) {
							EnemyDamageDealt = rand.nextInt(MaxEnemyDamage);
							PlayerHealth -= EnemyDamageDealt;
							System.out.println("You ran away, but the " + enemy + " dealt " + EnemyDamageDealt + " HP to you");
							Sleep(rand.nextInt(timeEnemyAppeared) + 1);
							
							if(rand.nextInt(100) < HealthPotDrop && PlayerHealth < 30) {
								numHealthPotion++;
								System.out.println("You found a health potion!");
								Sleep(1);
							}
							continue GAME;
						} else {
							System.out.println("You can't run away from a boss fight!");
							break;
						}
						
						
	//---------------------------------------------------------------------------------------------------------------------//
	   // DEFAULT
					default:
						break;
					}
	//---------------------------------------------------------------------------------------------------------------------//
				
// YOU WERE DEFEATED ------------------------------------------------------------------------------------------------------//
				if(PlayerHealth <= 0) {
					System.out.println("\nYou were defeated!");
					Sleep(1);
					PlayerLives -= 1;
					System.out.println("Lives Remaining: " + PlayerLives);
					Sleep(1);
					PlayerHealth = MaxPlayerHealth;				
				
					if(PlayerLives == 0) {
						System.out.println("Bosses killed: " + numBossesDefeated);
						System.out.println("Total monsters killed: " + numEnemiesDefeated);
						Sleep(1);
						System.out.println("Game Over!");
						running = false;
					} 
					
					continue;
				}
					
					
// ENEMY DEFEATED --------------------------------------------------------------------------------------------------------//
				if(enemyHealth <= 0) {
					// enemy drops random experience
					int ExpDropped = rand.nextInt(MaxExpDrop - MinExpDrop) + MinExpDrop;
					int HealthDropped = 0;
					int ArrowsDropped = 0;
					int BuffDropped = 0;
					int WeaknessDropped = 0;
					
					
					System.out.println("The " + enemy + " was defeated!\n");
					Sleep(2);
					
		// NORMIE DEFEATED ---------------------------------------------------------------------------------------------//
					if(!bossFight(numEnemiesDefeated)) {
						
			// Health Drop
						if(rand.nextInt(100) < HealthPotDrop*DropMulti) {
							HealthDropped = 1;
							numHealthPotion+=HealthDropped;
						}
						
			// Buff Drop
						if(rand.nextInt(100) < BuffPotDrop*DropMulti) {
							BuffDropped = 1;
							numBuffPotion+=BuffDropped;							
						}
						
			// Weakness Drop
						if(rand.nextInt(100) < WeakPotDrop*DropMulti) {
							WeaknessDropped = 1;
							numWeakPotion+=WeaknessDropped;
						}
			// Arrow Drop
						if(rand.nextInt(100) < ArrowDropRate*DropMulti) {
							ArrowsDropped = 1;
							TotalArrows+=ArrowsDropped;
						}
						
		    // XP Multiplier
						if(rand.nextInt(100) < ExpMultiChance) {
							System.out.println("An Experience orb was dropped! Your XP will double for a limited amount of time\n");
							startTime = new Date().getTime();
							ExpMulti=true;
						}
						
						System.out.println(enemy + "'s Loot: ");
						Sleep(0.5);
						System.out.println("   Health Potions: " + HealthDropped);
						System.out.println("     Buff Potions: " + ArrowsDropped);
						System.out.println(" Weakness Potions: " + WeaknessDropped);
						System.out.println("           Arrows: " + ArrowsDropped);

		// BOSS DEFEATED -----------------------------------------------------------------------------//
					} else if(bossFight(numEnemiesDefeated)) {
						
						// boss xp multiplier
						ExpDropped*=BossMultiplier;
					
			// Health Drop
						HealthDropped = rand.nextInt(4)+1;
						numHealthPotion+=HealthDropped;
						
			// Buff Drop
						if(rand.nextInt(100) < (BuffPotDrop*BossMultiplier)) {
							BuffDropped = 1;
							numBuffPotion+=BuffDropped;							
						}
						
			// Weakness Drop
						if(rand.nextInt(100) < WeakPotDrop) {
							WeaknessDropped = 1;
							numWeakPotion+=WeaknessDropped;
						}
						
			// Arrow Drop
						if(rand.nextInt(100) < (ArrowDropRate*BossMultiplier)) {
							ArrowsDropped = 1;
							TotalArrows+=ArrowsDropped;
						}
						
			// XP Multiplier
						if(rand.nextInt(100) < ExpMultiChance*BossMultiplier) {
							System.out.println("An Experience orb was dropped! Your XP will double for a limited amount of time\n");
							startTime = new Date().getTime();
							ExpMulti=true;
						}
						
						System.out.println(enemy + "'s Loot: ");
						Sleep(0.5);
						System.out.println("   Health Potions: " + HealthDropped);
						System.out.println("     Buff Potions: " + ArrowsDropped);
						System.out.println(" Weakness Potions: " + WeaknessDropped);
						System.out.println("           Arrows: " + BuffDropped);
						
						
						numBossesDefeated++;
						
					
						
						
					} // end boss fight statement
					 
					// checks for XP bonus
					if(Timer(startTime)) {
						ExpDropped*=ExpMultiplier;
					} else if(!Timer(startTime) && ExpMulti) {
						ExpMulti = false;
						System.out.println("XP bonus expired...");
					}
					
					// shows xp earned
					ExpRemaining-=ExpDropped;
					Sleep(2.5);
					System.out.println("\nYou earned " + ExpDropped + " XP\n");
					Sleep(1.5);
					
					// Player Level Up
					if(ExpRemaining <= 0) {
						ExpCarry = ExpRemaining;
						System.out.println("You leveled up!");
						Sleep(2.5);
						// set new xp level
						MaxExp*=(1+(PlayerLevel/3));
						ExpRemaining = MaxExp;
						ExpRemaining+= ExpCarry;
						// increase player stats
						PlayerLevel++;
						MaxPlayerHealth*=1.15;
						PlayerHealth = MaxPlayerHealth;
						MinMeleeDamage+=7;
						MaxMeleeDamage+=7;
						MinArrowDamage+=7;
						MaxArrowDamage+=7;
						// increase loot drop rate
						DropMulti+=(0.5/PlayerLevel);
						BossMultiplier+=(0.5/PlayerLevel);
						// After level, monsters get stronger
						MinBossDamage*=(1+(PlayerLevel/6));
						MaxBossDamage*=(1+(PlayerLevel/6));
						MaxEnemyDamage*=(1+(PlayerLevel/6));
						MinEnemyHealth*=(1+(PlayerLevel/6));
						MaxEnemyHealth*=(1+(PlayerLevel/6));
						MaxBossHealth*=(1+(PlayerLevel/5));
						MinBossHealth*=(1+(PlayerLevel/5));
						// increase Exp Drop
						MinExpDrop*=(1+(PlayerLevel/4));
						MaxExpDrop*=(1+(PlayerLevel/4));
						System.out.println("You are now player level "  + PlayerLevel + "\n");
					}
			// MAGIC UNLOCKED
					if(PlayerLevel == 5 && MagicUnlocked == false) {
						System.out.println("You begin to feel tingling throughout your body...");
						MagicUnlocked = true;
					}
					
					
					Sleep(1);
					System.out.println("Experience remaining until next level up: " + ExpRemaining + " XP\n");
					numEnemiesDefeated++;
					
			// ROUND RESETS
					
					Frozen = false;
					Buffed = false;		
					Weakened = false;
					Sleep(rand.nextInt(timeEnemyAppeared) + 1);
					
				}
				
				
			} // end while
		} // end game loop
	} // end main


} // end class

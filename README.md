# 🎲 Vanilla JS Tric-Trac

Vanilla JS implementation of the Backgammon variation Tric-Trac.

## Rules

- The game has two players: white and black.
- Each player has 15 checker.
- The board is a regular backgammon board.
- All checkers are initially placed outside board.
- The game uses two dice.
- The lower number of the dice must be plaied first.
- If the lower number of the dice cannot be played, the turn switches.
- If a player rolls a double (e.g. 1 + 1), the number is played four times (e.g. 4 * 1).
- If a player rolls a tric-trac, the player plays 2 * 1 & 2 * 2 & 2 * 5 & 2 * 6.
- Each player starts in their 1st quarter.
- A player can only move dice to the 2nd and 3rd quarter, if all player's dice are on the board.
- A player can only move dice into teh 4th quarter, if mo more dice are in the 1st quarter.
- All dice in the 4th quarter cannot be moved within that quarter.
- All dice in teh 4th quarter need to be thrown out with an exact number.
- A single checker in a row is unprotected and can be thrown out by the competitor.
- Two or more checker in a row are protected and blocking this row for the competitor.
- A checker that had been thrown out by the competitor must be brought in before making other moves.

## Checker states:

- Initial: The checker hasn't been brought on the board yet or had been thrown out by the competitor.
- Progress: The checker is currently on the board.
- Finished: The checker had been cleared from the board by the player.

## Dice states:

<table>
	<tr>
		<td>
			<table>
				<tr>
					<th>Roll</th>
					<th>Move</th>
				</tr>
				<tr>
					<td>1 | 1</td>
					<td>4 * 1</td>
				</tr>
				<tr>
					<td>1 | 2</td>
					<td>tric-trac</td>
				</tr>
				<tr>
					<td>1 | 3</td>
					<td>1 & 3</td>
				</tr>
				<tr>
					<td>1 | 4</td>
					<td>1 & 4</td>
				</tr>
				<tr>
					<td>1 | 5</td>
					<td>1 & 5</td>
				</tr>
				<tr>
					<td>1 | 6</td>
					<td>1 & 6</td>
				</tr>
			</table>
		</td>
		<td>
			<table>
				<tr>
					<th>Roll</th>
					<th>Move</th>
				</tr>
				<tr>
					<td>2 | 1</td>
					<td>tric-trac</td>
				</tr>
				<tr>
					<td>2 | 2</td>
					<td>4 * 2</td>
				</tr>
				<tr>
					<td>2 | 3</td>
					<td>2 & 3</td>
				</tr>
				<tr>
					<td>2 | 4</td>
					<td>2 & 4</td>
				</tr>
				<tr>
					<td>2 | 5</td>
					<td>2 & 5</td>
				</tr>
				<tr>
					<td>2 | 6</td>
					<td>2 & 6</td>
				</tr>
			</table>
		</td>
		<td>
			<table>
			<tr>
				<th>Roll</th>
				<th>Move</th>
			</tr>
			<tr>
				<td>3 | 1</td>
				<td>1 & 3</td>
			</tr>
			<tr>
				<td>3 | 2</td>
				<td>2 & 3</td>
			</tr>
			<tr>
				<td>3 | 3</td>
				<td>4 * 3</td>
			</tr>
			<tr>
				<td>3 | 4</td>
				<td>3 & 4</td>
			</tr>
			<tr>
				<td>3 | 5</td>
				<td>3 & 5</td>
			</tr>
			<tr>
				<td>3 | 6</td>
				<td>3 & 6</td>
			</tr>
		</table>
		</td>
		<td>
			<table>
				<tr>
					<th>Roll</th>
					<th>Move</th>
				</tr>
				<tr>
					<td>4 | 1</td>
					<td>1 & 4</td>
				</tr>
				<tr>
					<td>4 | 2</td>
					<td>2 & 4</td>
				</tr>
				<tr>
					<td>4 | 3</td>
					<td>3 & 4</td>
				</tr>
				<tr>
					<td>4 | 4</td>
					<td>4 * 4</td>
				</tr>
				<tr>
					<td>4 | 5</td>
					<td>4 & 5</td>
				</tr>
				<tr>
					<td>4 | 6</td>
					<td>4 & 6</td>
				</tr>
			</table>
		</td>
		<td>
			<table>
				<tr>
					<th>Roll</th>
					<th>Move</th>
				</tr>
				<tr>
					<td>5 | 1</td>
					<td>1 & 5</td>
				</tr>
				<tr>
					<td>5 | 2</td>
					<td>2 & 5</td>
				</tr>
				<tr>
					<td>5 | 3</td>
					<td>3 & 5</td>
				</tr>
				<tr>
					<td>5 | 4</td>
					<td>4 & 5</td>
				</tr>
				<tr>
					<td>5 | 5</td>
					<td>4 * 5</td>
				</tr>
				<tr>
					<td>5 | 6</td>
					<td>5 & 6</td>
				</tr>
			</table>
		</td>
		<td>
			<table>
				<tr>
					<th>Roll</th>
					<th>Move</th>
				</tr>
				<tr>
					<td>6 | 1</td>
					<td>1 & 6</td>
				</tr>
				<tr>
					<td>6 | 2</td>
					<td>2 & 6</td>
				</tr>
				<tr>
					<td>6 | 3</td>
					<td>3 & 6</td>
				</tr>
				<tr>
					<td>6 | 4</td>
					<td>4 & 6</td>
				</tr>
				<tr>
					<td>6 | 5</td>
					<td>5 & 6</td>
				</tr>
				<tr>
					<td>6 | 6</td>
					<td>4 * 6</td>
				</tr>
			</table>
		</td>
	</tr>
</table>

tric-trac = 2 * 1 & 2 * 2 & 2 * 5 & 2 * 6

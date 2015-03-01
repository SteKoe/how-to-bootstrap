# Grid system

Bootstrap bietet in der Standardkonfiguration ein Gittersystem mit 12 Spalten.
Die einzelnen Spalten werden - ähnlich wie bei einer Tabelle - in Zeilen eingeteilt.
Da Bootstrap darauf ausgelegt ist responsive Templates zu erlauben, ist gerade das Gridsystem bezüglich der Displaygröße hoch dynamisch, da je nach Größe die einzelnen Spalten anders dargestellt werden.
Dies ist darin begründet, dass auf einem Smartphone die Darstellung von mehreren Spalten nebeneinander zu keinem guten Ergebnis führen und die Spalten daher untereinander gerendert werden.

Um das Verhalten der einzelnen Spalten gezielt steuern zu können, bietet Bootstrap insgesamt 4 verschiedene CSS-Klassen an, mit welchen die Spalten definiert werden. 
Diese CSS-Klassen legen fest, wie sich die Spalten verhalten sollen, wenn die gesamte Breite aller Spalten bestimmte Ausmaße über- oder unterschreitet.
Die einzelnen Klassen lauten wie folgt:

<table>
	<thead>
		<tr>
			<th>Breite</th>
			<th>&lt;768px</th>
			<th>&ge;768px</th>
			<th>&ge;992px</th>
			<th>&ge;1200px</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Spaltenverhalten</td>
			<td>Immer horizontal</td>
			<td colspan="3">Horizontal, wenn Breite kleiner als oben angegeben, sonst nebeneinander.</td>
		</tr>
		<tr>
			<td><code>.container</code> Breite</td>
			<td>Automatisch</td>
			<td>750px</td>
			<td>970px</td>
			<td>1170px</td>
		</tr>
		<tr>
			<td>CSS-Klasse</td>
			<td><code>.col-xs-</code></td>
			<td><code>.col-sm-</code></td>
			<td><code>.col-md-</code></td>
			<td><code>.col-lg-</code></td>
		</tr>
	</tbody>
</table>


![alt text][grids_4_cols]

[grids_4_cols]: grids_4_cols.png "Layout mit 4 Spalten"

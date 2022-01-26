# Blood bowl team cards

Turns a standard html table of a blood bowl team roster into star player style
cards using mostly CSS, but falling back to SVG where not possible to create
the shapes needed.

Example team: [Loren Forest](http://bubble.swebba.com/lorenforest)

## Usage

1. Clone/download the repository
2. Edit the table in `index.html` to match your team status
3. Replace images 1-16 with photos of your own team players
4. Replace team.svg with your team logo
5. Replace coach.jpg with a picture of your coach miniature (or yourself!)
6. Open the index.html file in any web browser

### HTML expectations

The css expects rows and columns to be in the same format as in the
example index.html. Table thead and tfoot are optional, but tbody is mandatory.

Column ordering is crucial. Any extra columns must be **last**, after *value*.
This is to not require the user to add any css classes or other selectors to
the html. Exported html from excel should work, as long as the column ordering
is correct.

### Team logo

A team logo can be displayed in the background of the skills and injuries box.
The css will pick it up if is named `team.svg`. The image will be desaturated
and in very reduced opacity. For best results, use vector graphics for proper
scaling.

### Player photos

As long as a player photo exists in the same directory named as
`<table-row-number>.jpg`, the photo will be displayed on the card.
For best display result, keep the image roughly square, with a light:ish
background to not clash too badly with the red/blue backgrounds used.

The row number has nothing to do with the player number. Use player numbers
above 16 at your leisure. If you do want to strictly tie row numbers to players,
any jumps in player numbering must be coded as empty rows, `<tr></tr>`. The
example index.html uses this naming convention.

### Coach exception

The Coach has a separate set of labels for values, see tfoot for ordering.
These are meant to represent the staff, Team Re-rolls, dedicated fans,
assistant coaches, cheerleaders and apothecaries, as well as the league or
tournament standings.

It has to be the last table row, i.e. row number 17 for a full roster, or 12
for a starter roster. The coach photo has to be named `coach.jpg` and reside
in the same directory. The coach "number" refers to NAF membership numbers
and is thus reduced in size to fit.

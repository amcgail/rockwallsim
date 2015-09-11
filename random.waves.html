<style>
td {
 width: 23px;
 height: 23px;
}
body {
 background-color: black;
}
</style>

<body>

</body>

<script src='https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js'></script>
<script>
function between_arrays( a, b, t ) { //t between 0 and 1
 var newarr = [];
 for( var i in a ) {
  if( typeof b[i] != 'undefined' )
   newarr[i] = a[i] + t*( b[i] - a[i] );
 }
 return newarr;
}


var $byrc = [];
var $table = $("<table>");
for( var i=0; i<8; i++ ) {
 $byrc.push( [] );

 var $row = $("<tr>");
 for( var j=0; j<8*8; j++ ) {
  var $col = $("<td>").css( "background-color", "black" );
  $row.append( $col );

  $byrc[i].push( $col );
 }
 $table.append( $row );
}

$(document.body).append( $table );

function nextrc( r, c ) {
 if( r==7 && c==8*8-8 )
  return null;

 if( c%8==0 && r%2==1 ) {
  if( r==7 )
   return [0,c+8];
  return [r+1,c];
 }

 if( c%8==7 && r%2==0 )
  return [r+1,c];

 if( r%2==0 )
  return [r,c+1];

 return [r,c-1];
}

var byrc=[];
for( var i=0; i<8; i++ ) byrc.push( [] );

var rc2i = {};

function build( r,c,i ) {
 rc2i[ r + "," + c ] = i;

 var nrc = nextrc( r,c );
 var nx = null;
 if( nrc != null )
  nx = build( nrc[0], nrc[1], ++i );

 var built = {
  //Current physical properties
  jQ: $byrc[r][c],
  color: [0,0,0],

  //This is the only light I can communicate with
  next: nx,

  //Impliments tweening
  targets: [],

  command_nolatency: function( i, color, start_time, timeout ) {
   if( i==0 ) {
    this.targets.push( {
     c: color,
     s: start_time,
     d: timeout
    } );
   } else
    this.next.command_nolatency( --i, color, start_time, timeout );
  },

  //Class functions
  command: function ( i, color, start_time, timeout ) {
   var _th = this;
   setTimeout( function() {
    _th.command_nolatency( i, color, start_time, timeout );
   }, 5*i );
  },
  set_color: function(color) {
   this.color = color.map( function(x) { return Math.floor( x ); } );
   this.jQ.css( "background-color", "rgb( " + this.color[0] + ", " + this.color[1] + ", " + this.color[2] + " )" );
  }
 };

 //Create hook for this object and return it
 byrc[r][c] = built;
 return built;
};

//Begin building at the origin. They will wind through the whole wall
build( 0, 0, 0 );

setInterval( function() {
 //On
 for( var c=0; c<8*8; c++ ) {
  for( var r=0; r<8; r++ ) {
   var i = rc2i[r+','+c];
   byrc[0][0].command( rc2i[r+','+c], [255,255,0], 100*c + 2560 - i*5, 1000 );
  }
 }

 //Onlonger
 for( var c=0; c<8*8; c++ ) {
  for( var r=0; r<8; r++ ) {
   var i = rc2i[r+','+c];
   byrc[0][0].command( rc2i[r+','+c], [255,255,0], 1000+100*c + 2560 - i*5, 500 );
  }
 }

 //Off
 for( var c=0; c<8*8; c++ ) {
  for( var r=0; r<8; r++ ) {
   var i = rc2i[r+','+c];
   byrc[0][0].command( rc2i[r+','+c], [Math.random()*256,Math.random()*256,Math.random()*256], 1500 + 100*c + 2560 - i*5, 500 );
  }
 }
}, 3000 );

/*
//LET'S TRY TO GET CONSTANT TIMING DOWN
for( var i=0; i<8*8*8; i++ )
 byrc[0][0].command( i, [255, 255, 0], 2560 - i*5, 2000 );
*/

/*
//A SIMULATION OF HAVING DRIVERS AT EACH WALL SEGMENT.
//I DON'T KNOW OF A GOOD WAY TO DO THIS ONE
for( var i=0; i<8; i++ )
 for( var j=0; j<8*8; j++ )
  byrc[0][8*i].command( j, [255, 255, 0], 3000, 2000 );
*/

function timestep() {
 for( var i in byrc )
  for( var j in byrc[i] ) {
   var o = byrc[i][j];

   //act on the minimum
   var minv = null;
   var mini = -1;
   for( var ti in o.targets ) {
    var t = o.targets[ti];
    if( t.s > 0 )
     continue;

    if( minv == null || o.targets[ti].d < minv ) {
     minv = o.targets[ti].d;
     mini = ti;
    }

   }

   if( mini != -1 ) { 

    var mint = o.targets[ mini ];
    if( mint.d <= 1000 / 25 ) //less than one sample width
     o.set_color( mint.c );
    else {
     o.set_color( between_arrays( o.color, mint.c, (1000/25) / mint.d ) );
    }

    mint.d -= 1000 / 25;

   }

   //cleanup and update
   for( var ti=0; ti<o.targets.length; ) {
    var t = o.targets[ti];

    if( t.d < 0 ) {
     o.targets.splice(ti,1);
    } else {
     ti++;
    }

    if( t.s > 0 ) {
     t.s -= 1000 / 25;
     continue;
    }
   }

  }
}

setInterval( timestep, 1000 / 25 );
</script>

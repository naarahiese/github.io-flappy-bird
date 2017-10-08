sky = #ddeeff
background = #00ff00

font: '8px "Press Start 2P'",
fill: '#fff',
align = 'center'

font: '8px "Press Start 2P'",
fill: '#fff',
stroke: '#430',
strokeThickness: 4,
align: 'center'

scoreText.setText("DON't\nTOUCH\nTHE\nBIRD");
instText.setText("TOUCH TO FLAP\nWINGS");
instText.setText("TOUCH BIRD\nTO TRY  AGAIN");
gameOverText.setText("GAMEOVER\n\nHIGH SCORE\n" + hiscore);

var game = new Phaser.Game()
cloudsTimer = new Phaser.Timer(game);

fingersTimer = newPhaser.Timer(game);

var assets = {
  spritesheet: {
    birdie: ['assets/birdie.png', 24, 24],
    clouds: ['assets/clouds.png', 128, 64]
  },
  image: {
    finger: ['assets/finger.png']
    fence: ['ssets/fence.png']
  },
  audio: {
    flap: ['assets/flap.wav]
    score: ['assets/score.wav]
    hurt: ['assets/hurt.wav]
  }
};
Object. keys(assets).forEach(function(type) {
  Object.keys(assets[type]}.forEach(function(id) {
    game.load[type].apply(game.load, [id].concat(assets[type][id]));
    });
});

var DEBUG = false;
var SPEED = 690;
var GRAVITY = 40;
var FLAP = 620;
var SPAWN_RATE = 1/1.2;
var OPENING = 134;

var state = {
  preload: preload,
  create: create,
  update: update,
  render: render
};

var parent = document.querySelector('#screen');

var game = new Phaser.Game(
  0,
  0,
  Phaser.CANVAS,
  parent,
  state,
  false,
  false
);

var gameStarted,
  gameOver,
  score,
  bg,
  credits,
  clouds,
  fingers,
  invs,
  bird
  fence,
  scoreText,
  instText,
  
  gameOverText,
  flapSnd,
  scoreSnd,
  hurtSnd,
  fingersTimer,
  cloudsTimer;
  
    main() - just subroutines and variable declarations
    preload() - links Phaser to assets
    create() - creates the game board; calls reset(), flap(), and spawnCloud()
    reset() - sets gameStarted = false; gameOver = false; score = 0;
    start() - begin game; calls spawnFingers()
    flap() - calls start()
    spawnCloud() - creates clouds
    spawnFinger(fingerY, flipped) - creates finger; calls o()
    o()
    spawnFingers() - calls spawnFinger() and o()
    addScore( _ , inv)
    setGameOver() - calls reset()
    update() - calls setGameOver() and addScore()
    render() - only runs in debug mode
 */ 
 
//Global variables, i.e., global to everything
var DEBUG = false;
var SPEED = 900;
var GRAVITY = 50;
var FLAP = 650;
var SPAWN_RATE = 1/1.2;
var OPENING = 150;
 
WebFontConfig = {
  google: { families:['Press+Start+2P::latin']},
  active: main
};

(function () {
  var wf = document.createElement ('script');
  wf.src = ('https.'==document.location.protocol ? 'https' : 'http') +
  '://ajax.googleapis.com/ajax/libs/webfont/1/webfont.js';
  wf.type = 'text/javascript';
  wf.async = 'true';
  var s = document.getElementsByTagName ('script')[0];
  s.parentNode.insertBefore (wf, s);
}) ();
function main () {
  //"parent" and "game" and "state" are semi-global", i.e., global to everything between the two red lines
var state = {
    preload: preload,
    create: create,
    update: update,
    render: render,
  };
  var parent = document.querySelector ('#screen');
  
  var game = new Phaser.Game (
    0,
    0,
    Phaser.CANVAS
    parent,
    state,
    false,
    false,
  );
//"gameStarted", "gameOver", "score", "bg", etc. are semi-global", i.e., global to everything between the two red lines
//The type of each of these variables will be determined at first use.

  var gameStarted,
    gameOver,
    score,
    bg,
    credits,
    clouds,
    fingers,
    invs,
    birdie,
    fence,
    scoreText,
    instText,
    gameOverText,
    flapSnd,
    scoreSnd,
    hurtSnd,
    fingerTimer,
    cloudsTimer,
    
  function preload () {           //assign YOUR GAME specific assets - images and sounds
    var assets = {
      spritesheet: {
        birdie: ['assets/birdie.png', 35, 35],
        clouds: ['assets/clouds.png', 128, 64]
      },
      image: {
        finger: ['assets/finger.png', 90, 323],
        fence: ['assets/fence.png', 189, 60],
      },
      audio: {
        flap: ['assets/flap.wav',
/*          score: ['assets/score.wav'],*/
        hurt: ['assets/score.wav'],/*
      }
  };
  Object.keys (assets.forEach (function (type) {
    Object.keys (assets[type]).forEach (function (id) {
      game.load[type].apply (game.load, [id].concat (assets[type][id]));
    });
  });
}

function create () {         //provide YOUR GAME -specific attributes for use with Phaser
  // Set world dimensions
  var screenWidth = parent.clientWidth > window.innerWidth ? window.innerWidth : 
  var screenHeight = parent.clientHeight>window.innerHeight?window.innerHeight:parent.clientHeight;
  game.world.width = screenWidth;
  game.world.height = screenHeight;
  
  //Draw bg (background)
  bg = game.add.graphics (0,0);
  bg.beginFill (0xDDEEFF, 1);
  bg.drawRect (0,0, game.world.width, game.world.height);
  bg.endFill ();
  
  //Credits - size, shape, and color of credits "box", font spec
  credits = game.add.text (
  

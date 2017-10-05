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

var 

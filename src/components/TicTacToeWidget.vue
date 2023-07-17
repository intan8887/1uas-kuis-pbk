<template>
    <div class="tic-tac-toe-widget">
      <h2>Tic Tac Toe</h2>
      <div class="board">
        <div v-for="(cell, index) in board" :key="index" @click="handleClick(index)">{{ cell }}</div>
      </div>
      <button @click="resetGame">Reset</button>
      <p>{{ status }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        board: ['', '', '', '', '', '', '', '', ''],
        currentPlayer: 'X',
        isGameEnded: false,
      };
    },
    computed: {
      status() {
        if (this.isGameEnded) {
          return 'Game Over!';
        }
        return `Player ${this.currentPlayer}'s turn`;
      },
    },
    methods: {
      handleClick(index) {
        if (!this.isGameEnded && this.board[index] === '') {
          this.board[index] = this.currentPlayer;
          this.checkWinner();
          this.currentPlayer = this.currentPlayer === 'X' ? 'O' : 'X';
        }
      },
      checkWinner() {
        const winningCombinations = [
          [0, 1, 2], [3, 4, 5], [6, 7, 8], // Rows
          [0, 3, 6], [1, 4, 7], [2, 5, 8], // Columns
          [0, 4, 8], [2, 4, 6], // Diagonals
        ];
  
        for (const combination of winningCombinations) {
          const [a, b, c] = combination;
          if (this.board[a] && this.board[a] === this.board[b] && this.board[a] === this.board[c]) {
            this.isGameEnded = true;
            return;
          }
        }
      },
      resetGame() {
        this.board = ['', '', '', '', '', '', '', '', ''];
        this.currentPlayer = 'X';
        this.isGameEnded = false;
      },
    },
  };
  </script>
  
  <style scoped>
  .tic-tac-toe-widget {
    border: 1px solid #f13737;
    padding: 20px;
    margin-bottom: 20px;
    background-image: url(https://media.istockphoto.com/id/1217676743/id/vektor/game-pc-aksesoris-desain-wallpaper-sampul-teknologi-garis-pada-latar-belakang-putih-template.jpg?s=1024x1024&w=is&k=20&c=7M66JJmnry8w7_M5EMSd455BWXRLLIAFE3UG0KlejRU=);
  }
  
  .board {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 10px;
    margin-bottom: 10px;
  }
  
  .board div {
    border: 1px solid #182468;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background-image: url(data:image/jpeg;base64,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);
  }
  .tic-tac-toe-widget h2{
      color: #182468;
  }
  button {
    margin-top: 10px;
  }
  </style>
  
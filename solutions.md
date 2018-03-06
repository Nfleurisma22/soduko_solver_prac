### Look at these inside a text editor

## Python

def done_or_not(board):
  rows = board
  cols = [map(lambda x: x[i], board) for i in range(9)]
  squares = [
    board[i][j:j + 3] + board[i + 1][j:j + 3] + board[i + 2][j:j + 3]
      for i in range(0, 9, 3)
      for j in range(0, 9, 3)]

  for clusters in (rows, cols, squares):
    for cluster in clusters:
      if len(set(cluster)) != 9:
        return 'Try again!'
  return 'Finished!'


## JS

const isValidList = (list) => {
  return list.every(Boolean) &&
         list
          .slice()
          .sort((a, b) => a-b)
          .every((item, index, list) => item !== list[index + 1])
}

const invertBoard = (board) => {
  return board.reduce((prev, curr) => {
    curr.forEach((value, index) => {
      prev[index] = prev[index] || [];
      prev[index].push(value);
    });

    return prev;
  }, []);
};

const boardRegions = (board) => {
  return board.reduce((prev, curr, index) => {
    const lastItem = prev.slice(-1)[0],
          regionsSlice = (lastItem && lastItem.length !== 9) ?
                          prev.splice(-3) :
                          [ [], [], [] ];

    return prev.concat(regionsSlice.map((item, i) => {
      const start = i * 3;
      return item.concat(curr.slice(start, start + 3))
    }))
  }, []);
};

const doneOrNot = (board) => {
  return (
    board.every(isValidList) &&
    invertBoard(board).every(isValidList) &&
    boardRegions(board).every(isValidList)
  ) ? 'Finished!' : 'Try again!';
};

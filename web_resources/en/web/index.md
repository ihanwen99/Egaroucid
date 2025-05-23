# Egaroucid for Web

<div align="center" style="line-height: 1.5;">
    <span id="ai_info">AI Initializing...</span><span>If loading doesn't finish in 10 seconds, please reload.</span>
</div>
<div align="center">
    <table class="settings_table">
        <tr class="settings_table">
            <td class="settings_table"><label><input type="radio" class="radio_size" name="ai_player" value="1" id="white" checked><span class="setting">Black(First): You White(Second): AI</span></label></td>
        </tr>
        <tr class="settings_table">
            <td class="settings_table"><label><input type="radio" class="radio_size" name="ai_player" value="0" id="black"><span class="setting">Black(First): AI White(Second): You</span></label></td>
        </tr>
    </table>
</div>
<div align="center">
    <label>
        <span class="setting">Strength</span>
        <input type="range" id="ai_level" min="0" max="15" step="1" value="7">
    </label>
    <span class="setting" id="ai_level_label"></span>
</div>
<div align="center">
    <table class="settings_table">
        <tr class="settings_table">
            <td class="settings_table"><label><input type="checkbox" id="show_value" unchecked><span class="setting">Hint</span></label></td>
            <td class="settings_table"><label><input type="checkbox" id="show_graph" checked><span class="setting">Graph</span></label></td>
        </tr>
        <tr class="settings_table">
            <td class="settings_table"><label><input type="checkbox" id="show_legal" checked><span class="setting">Moves</span></label></td>
            <td class="settings_table"><label><input type="checkbox" id="auto_pass" checked><span class="setting">Auto-Pass</span></label></td>
        </tr>
    </table>
</div>
<div align="center">
    <div class="buttons">
        <input type="submit" class="setting" value="Start" onclick="start()" id="start" disabled>
        <input type="submit" class="setting" value="Reset" onclick="reset()" id="reset" disabled>
        <input type="submit" class="setting" value="Pass" onclick="pass()" id="pass" disabled>
    </div>
</div>
<div class="popup" id="js-popup">
    <div class="popup-inner">
        <p align="center" class="sub_title" id="result_text"></p>
        <img class="image" id="game_result" width="80%" height="auto" style="aspect-ratio: 1.06;">
        <p align="center" class="hidden" id="tweet_result"></p>
        <p align="center" class="text">You can save this picture</p>
        <p align="center" class="text">Click black area to close</p>
    </div>
    <div class="black-background" id="js-black-bg"></div>
</div>
<div class="div_main">
    <table class="table_board" align="center" id="table_board"></table>
    <table class="status" id="status" align="center">
        <tr>
            <td class="status_cell"><span class="state_blank"></span></td>
            <td class="status_cell"><span class="black_stone"></span></td>
            <td class="status_char"><span class="state_blank">2</span></td>
            <td class="status_char"><span class="state_blank">-</span></td>
            <td class="status_char"><span class="state_blank">2</span></td>
            <td class="status_cell"><span class="white_stone"></span></td>
            <td class="status_cell"><span class="state_blank"></span></td>
        </tr>
    </table>
</div>
<div id="info" class="info">
    <div class="sub_title">Game Information</div>
    <div class="sub_sub_title">Graph</div>
    <div class="chart" id="chart_container">
        <canvas id="graph"></canvas>
    </div>
    <div class="sub_sub_title">Transcript</div>
    <div class="record" id="record"></div>
</div>
<div align="center">
    <p>This is simplified version and weaker than [download version](./../download/). Also, this version has very few features. You can use full rich features with download version.</p>
    <div class="sub_title">Usage</div>
    <div class="text">
        Select your turn and AI strength, then press "Start" button.<br>
        Graph shows how good the AI seems to be. If the value is big, AI seems to win. If small, you seems to win.<br>
        You can check the graph after the game though you don't check the "Graph" checkbox.<br>
        Though you use level 8 or more, hint values are calculated in no more than level 8.<br>
    </div>
    <p></p>
    <div class="sub_title">Strength</div>
    <div class="text">
        Strength is adjusted by midgame lookahead, endgame lookahead, and depth of perfect searching. 
        If you use high level, the calculation time will be long.
    </div>
    <div class="table_wrapper">
        <table>
            <tr>
                <th class="text">Level</th>
                <th class="text">midgame depth</th>
                <th class="text">endgame depth</th>
                <th class="text">perfect search</th>
            </tr>
            <tr>
                <td class="text">0</td>
                <td class="text">0 moves</td>
                <td class="text">0 moves</td>
                <td class="text">0 moves</td>
            </tr>
            <tr>
                <td class="text">1</td>
                <td class="text">1 moves</td>
                <td class="text">2 moves</td>
                <td class="text">2 moves</td>
            </tr>
            <tr>
                <td class="text">2</td>
                <td class="text">2 moves</td>
                <td class="text">4 moves</td>
                <td class="text">4 moves</td>
            </tr>
            <tr>
                <td class="text">3</td>
                <td class="text">3 moves</td>
                <td class="text">6 moves</td>
                <td class="text">6 moves</td>
            </tr>
            <tr>
                <td class="text">4</td>
                <td class="text">4 moves</td>
                <td class="text">8 moves</td>
                <td class="text">8 moves</td>
            </tr>
            <tr>
                <td class="text">5</td>
                <td class="text">5 moves</td>
                <td class="text">10 moves</td>
                <td class="text">10 moves</td>
            </tr>
            <tr>
                <td class="text">6</td>
                <td class="text">6 moves</td>
                <td class="text">12 moves</td>
                <td class="text">12 moves</td>
            </tr>
            <tr>
                <td class="text">7</td>
                <td class="text">7 moves</td>
                <td class="text">14 moves</td>
                <td class="text">14 moves</td>
            </tr>
            <tr>
                <td class="text">8</td>
                <td class="text">8 moves</td>
                <td class="text">16 moves</td>
                <td class="text">16 moves</td>
            </tr>
            <tr>
                <td class="text">9</td>
                <td class="text">9 moves</td>
                <td class="text">18 moves</td>
                <td class="text">18 moves</td>
            </tr>
            <tr>
                <td class="text">10</td>
                <td class="text">10 moves</td>
                <td class="text">20 moves</td>
                <td class="text">20 moves</td>
            </tr>
            <tr>
                <td class="text">11</td>
                <td class="text">11 moves</td>
                <td class="text">20 moves</td>
                <td class="text">20 moves</td>
            </tr>
            <tr>
                <td class="text">12</td>
                <td class="text">12 moves</td>
                <td class="text">22 moves</td>
                <td class="text">20 moves</td>
            </tr>
            <tr>
                <td class="text">13</td>
                <td class="text">13 moves</td>
                <td class="text">22 moves</td>
                <td class="text">20 moves</td>
            </tr>
            <tr>
                <td class="text">14</td>
                <td class="text">14 moves</td>
                <td class="text">24 moves</td>
                <td class="text">22 moves</td>
            </tr>
            <tr>
                <td class="text">15</td>
                <td class="text">15 moves</td>
                <td class="text">24 moves</td>
                <td class="text">22 moves</td>
            </tr>
        </table>
    </div>
    <div class="text">
        Last Updated: 2025/02/05 Evaluation Function Update
    </div>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.2/Chart.bundle.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/0.4.1/html2canvas.js"></script>
<script src="script.js"></script>


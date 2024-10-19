# mermaid-program-example
Examples of Mermaid diagram that represents programs


## Flowchart with subgraph  
Repo:
https://github.com/WingTillDie/battery-level-wsl/tree/main

```mermaid
flowchart TD
    Start([Start]) --> For
    For{{Enter Infinite Loop}}
    subgraph Print[Print Battery Level]
        assert_cursor_start[assert: Cursor is at Start of the Line]
        assert_cursor_start --> Overwrite
        Overwrite[/Print Updated Battery Level by Overwriting Previous Battery Level/]
        Overwrite --> assert_cursor_end
        assert_cursor_end[assert: Cursor is at End of the Line]
        assert_cursor_end --> CR
        CR[/Move Cursor to Start of the Line/]
        CR --> Sleep
        Sleep[Sleep for 1 second]
    end
    For --> Print
    Sleep --> For
```


## Flowchart with link label  
Repo:
https://github.com/WingTillDie/warn-no-network-windows
```mermaid
flowchart TD
    Forever{{Forever}}
    ping[Get Connectivity Status]
    Forever --> ping
    ping --> If
    If{Is Connected?}
    Connected[/Print Has Network/]
    Sleep[Sleep 1 Minute]
    Connected --> Sleep
    Disconnected[/Print No network/]
    Pause[\Pause/]
    Disconnected --> Pause
    If -->|Yes| Connected
    If --> |No| Disconnected
    Sleep --> join
    Pause --> join
    join(( ))
    join --> Forever
```

## Entity Relationship Diagram  
Repo:
https://github.com/WingTillDie/youtube-video-length
```mermaid
erDiagram
    "All YouTube Videos" ||..o| "YouTube Videos with Matched Length" : "contains"
    "All YouTube Videos" ||..o| "YouTube Videos with Specified Search String" : "contains"
    "YouTube Videos with Specified Search String" ||..o| "YouTube Videos with Specified Search String, Top 100 Results": "contains"
    "YouTube Videos with Specified Search String, Top 100 Results" ||..o| "YouTube Videos with Specified Search String, Top 100 Results, with Match Length" : "contains"
    "YouTube Videos with Specified Search String, Top 100 Results" ||..o| "YouTube Videos with Specified Search String, Top 100 Results, with Not Match Length" : "contains"
    "YouTube Videos with Matched Length" ||..o| "YouTube Videos with Specified Search String, Top 100 Results, with Match Length" : "contains"
```

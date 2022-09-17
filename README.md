# SA-MP-MultiThread
Multithreading by Fro1sha

Natives:
```cpp
native CreateThread(const pubname[]);
native CreateThreadEx(const pubname[]);
native DestroyThread(threadid);
native SleepThread(milliseconds); // Use em threads (public)
native LockThread(threadid); // Sincronizar e retornar id do bloqueio
native UnLockThread(lockid);```

```pawn
new tickid;

public OnGameModeInit()
{
	tickid = CreateThread("MyFunction");
}

public OnGameModeExit()
{
	DestroyThread(tickid);
}

public MyFunction(threadid)
{
	printf("tick(%d)...", threadid );
	SleepThread(1000);
}```


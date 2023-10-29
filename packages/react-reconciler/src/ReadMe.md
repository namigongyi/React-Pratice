1.useEffect 和 useLayoutEffect都是同一个类型
2.只是大家的执行时间不同
3.大家共用 updateEffectImpl,只是执行时间不同
3.1 在renderHooks里把 currentlyRendering.updateQueue 制成null
4.判断nextDeps = deps === undefined ? null :deps
5.判断初次渲染还是更新阶段，根据 currentHook !== null
5.1 根据currentHooks.memoizedState 判断是否依赖又没变化 
6.在next上把 hooks的链表挂载上去（fiber上也有一个hooks链表，这里是为了方便拿
7.在currentlyRendering.updateQueue上拿到单向循环链表
6.把单向循环链表断开,把新的effect 接到尾部，然后缝上。



1.fiber
1.1 fiber tree
1.1.1 how to update a fiber tree (Scheduler)
1.1.2 Yield the main thread
1.1 fiber.memoizedState
2.fiberRoot
3.hook
3.1  hook.memoizedState
4.update
5.effect


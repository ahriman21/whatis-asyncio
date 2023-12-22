## what is asyncio library :
* it is a library to write asynchronous applications in python.
* asyncio uses one thread to manage several tasks.
* an asyncronous function is called coroutine. you can create coroutine by using `async` keyword before defining a function like `async def foo(): ...`.
* there is something in asyncio called `eventloop`. its resposibility is to loop over existing tasks.
* when you use keyword `await` it means event-loop defines this spot as an I/O bound and will go through another task instead of waiting for that process.
* after creating coroutines we must submit each of them as a task in eventloop.
to do that, we mostly create an async function named `main` and submit all coroutines in it, then we run the main function by using `asyncio.run(main())`



## create a coroutine
```python
# for example this coroutine uploads an image that takes 4 seconds 
async def upload_image():
  await asyncio.sleep(4)
```

## create task (submit the coroutine as a task in eventloop)
```python

async def main():
  task1 = asyncio.create_task(upload_image())
  await task1
```

## run the tasks :
```python
asyncio.run(main())
```
 


## create a group of tasks
we can create a group of tasks in 3 ways

* gather
> in this way if one of the tasks raises exeption, the rest of tasks can not be executed, but you can solve this problem by `return_exceptions=True` as the last parameter of `gather()`
```python
async def main():
    tasks = await asyncio.gather(
        func1(),
        func2(),
        func3(),
        return_exceptions=True
    )
```

* TaskGroup
```python
# Defining main function 
async def main(): 
    async with asyncio.TaskGroup() as task_group: 
        task_group.create_task(func1()) 
        task_group.create_task(func2()) 
  
# calling main function 
asyncio.run(main())
```



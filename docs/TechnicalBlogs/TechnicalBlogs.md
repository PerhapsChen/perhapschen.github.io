# Technical Blog

---



# Notebook to HTML file

**convert `.ipynb` file as `HTML` file.**

```bash
jupyter nbconvert --to html ./foobar.ipynb
```

The following formats are available: 

```bash
['asciidoc', 'custom', 'html', 'latex', 'markdown', 'notebook', 'pdf', 'python', 'qtpdf', 'qtpng', 'rst', 'script', 'slides', 'webpdf']   
```

In the HTML file, we can modify `jp-code-font-size` to change font size of codes.

---



# VSCode remote-ssh 免密

参考: [配置vscode 远程开发+ 免密登录 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/222452460)

---



# 使用format参数加速pd.to_datetime转换

`pd.to_datetime` 会自己检测用了哪种格式，这种检测需要花费大量时间，可以给定固定格式进而加速。

```python
df.index=pd.to_datetime(df.index,format='%Y-%m-%d %H:%M:%S.%f')
```

# 异步IO

!> 这部分内容来自ChatGPT的回答：现在我需要读取4000个大小为100M的文件，并对每个文件进行一些计算，怎么做比较快？

对于这种需要读取大量文件并进行计算的任务，可以考虑使用异步IO来提高效率。异步IO允许程序在等待IO操作完成的同时继续执行其他任务，从而更加高效地利用CPU和IO资源。以下是一个可能的实现方案：

1. 使用asyncio模块来实现异步IO操作。
2. 使用aiofiles模块来读取文件，它提供了异步IO的文件读取功能。
3. 对于每个文件，使用asyncio.create_task()方法创建一个协程任务，并将其加入到事件循环中。
4. 在协程任务中进行文件读取和计算操作，完成后返回结果。
5. 使用asyncio.gather()方法来等待所有协程任务完成，并获取计算结果。

下面是一个示例代码：

```python
import asyncio
import aiofiles

async def process_file(filename):
    async with aiofiles.open(filename, 'rb') as f:
        data = await f.read()
        # 进行计算操作
        result = len(data)
        return result

async def main():
    filenames = ['file{}.dat'.format(i) for i in range(4000)]
    tasks = [asyncio.create_task(process_file(filename)) for filename in filenames]
    results = await asyncio.gather(*tasks)
    # 处理计算结果
    total = sum(results)
    print(total)

if __name__ == '__main__':
    asyncio.run(main())
```

在这个示例代码中，我们使用了asyncio模块来实现异步IO操作，使用aiofiles模块来读取文件，对于每个文件创建一个协程任务，并使用asyncio.gather()方法来等待所有协程任务完成。这样可以同时读取多个文件，从而提高效率。

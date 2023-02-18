```python



"""
Author: Mark

date: 2023/2/18 22:43
"""
# 引入模块
from pynput.keyboard import Key, Controller as keyboard_controller
from pynput.mouse import Button, Controller as mouse_controller
import time

def auto_input(content):
    """

    :param content: 输入在发送框的内容
    :return: None
    """
    # 开始控制键盘
    keyboard = keyboard_controller()  # 开始控制键盘
    keyboard.type(content)  # 模拟键入
    # 回车键，发送消息。点击和回车只能选一种
    keyboard.press(Key.enter)


def auto_click():
    mouse = mouse_controller()
    mouse.press(Button.left)  # 按住鼠标左键
    mouse.release(Button.left)  # 放开鼠标左键


def main(number, content):
    """
    主程序
    :param number:表示要发送多少条信息
    :param content:表示要发送的内容
    :return:None
    """
    # 此时暂停5s,用来打开聊天窗口，并把鼠标停放在发送按钮上
    time.sleep(5)
    for i in range(number):
        auto_input(content + ' ' + str(i+1))
        # 通过点击按钮来发送
        # auto_click()
        # 间隔时间
        time.sleep(0.6)


if __name__ == '__main__':
    main(5, '牧天白衣')



```

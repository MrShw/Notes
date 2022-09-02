# 一、Understanding Linux Concepts

定义变量不用/\$，引用变量用/$

{}里面表示变量，定义时可选，加不加都行，加上是为了帮助解释器识别变量边界

```powershell
for file in $(ls ./);
	do if [ $file == 'hello' ];
	   then echo 'yes';
	   else echo 'no';
	   fi;
	done
```

[ -e 路径 ] 文件是否存在

[ -d 路径 ] 是否是目录

grep "字符" -n 路径 1 路径 2

ls: -lahp l：lst a：all h：size p：注明文件夹

cp -rfiav a：复制目录用，留权限 v：显示复制文件夹

mv -nf n：不覆盖 f：不询问 i：询问

mk -p p：创建依赖文件夹

rm -rfid d：空目录 i：询问

grep -invchw i：不区分大小写 n：行数 c：计数 v：取反 w：完全匹配 h：不显示文件名

tar -zcvf c：打包压缩 x：解压 v：显示信息 f：指定文件名 C：指定目录

chmod ugoa+-rwx-

cat

find ./ -name "intro.txt"

wc -l l：行数 w：单词计数

sed -nei n：显示处理结果 e：制定 scrip 处理文件 i：修改原文件

sed -nei '3,5adcpI' words a：插入 d：删除 c：替换 p：打印 /关键字

/key/
/rex/
I:case insensive

sed -n 's/old/new/g' words s：一个字符替换另一个字符 g：全局

sed -n '/[0-9]/p' filename 将文件中匹配数字的行打印出来
sed -n '/[a-z]/p' filename 将文件中匹配小写字母的行打印出来
sed -n '/[A-Z]/p' filename 将文件中匹配大写字母的行打印出来

sed -i '/[0-9]/d' filename 将文件中匹配数字的行删除
sed -n '/[a-z]/d' filename 将文件中匹配小写字母的行删除
sed -n '/[A-Z]/d' filename 将文件中匹配大写字母的行删除

sed -i '/[0-9]/s/root/huoqiu/g' filename 将文件中匹配数字的行里的 root 替换为 huoqiu
sed -i '/[a-z]/s/root/huoqiu/g' filename 将文件中匹配小写字母的行里的 root 替换为 huoqiu
sed -i '/[A-Z]/s/root/huoqiu/g' filename 将文件中匹配大写字母的行里的 root 替换为 huoqiu

## 1. Linux 发型版本

6 个版本 Linux 最流行：

```
1. RedHat, 提供技术支持和修复服务，收费
2. CentOS, 免费，与Redhat一样，但是没有技术服务
3. Fedora, ponsored by RedHat
4. Suse owned by Novell
5. debian, pc端很流行
6. Ubuntu, 最常见的
```

## 2. Virtual BOX

Virtual Box 是一个免费和开源的 x86 计算机管理程序。目前由甲骨文公司开发。

它可以安装在你现有的基于 Intel 或 AMD 的计算机上。无论它们是运行 Windows、Mac、Linux 还是 Solaris 操作系统。它扩展了你现有计算机的能力，使其能够运行多个操作系统。它扩展了你现有计算机的功能，使其能够在一个硬件上运行多个操作系统 硬件上同时运行多个操作系统

# 二、Download, Install and Configure

主要涉及以下命令

```
tar	    压缩和解压缩命令
        -c	创建打包文件
        -v	显示打包或者解包的详细信息
        -f	指定文件名称, 必须放到所有选项后面
        -z	压缩或解压缩(.gz)
        -j	压缩或解压缩(.bz2)
        -x	解包
        -C	解压缩到指定目录

zip	    压缩成.zip格式文件
unzip	解压缩.zip格式文件
        -d	解压缩到指定目录

```

# 三、System Access and File System

主要涉及以下命令

```
- man： 查看命令手册
- help：查看帮助
- pwd：	显示当前工作目录
```

# 四、Linux 初级命令

主要涉及以下命令

```
ls	            查看当前目录信息
pwd	            查看当前目录路径
cd ~	        切换到当前用户的主目录
cd ..	        切换到上一级目录
cd .	        切换到当前目录
cd -	        切换到上一次目录
touch 文件名	 创建指定文件
mkdir 目录名	 创建目录(文件夹)
rm 文件名    	 删除指定文件或者目录
rmdir 目录名	 删除空目录
cp	拷贝文件、拷贝目录
mv	移动文件、移动目录、重命名
```

ls 命令选项使用

```
-l	以列表方式显示
-h	件大小单位显示，默认是字节
-a	显示隐藏文件和隐藏目录
```

rm 命令选项使用

```
-i	交互式提示
-r	递归删除目录及其内容
-f	强制删除，忽略不存在的文件，无需提示
-d	删除空目录
```

cp 命令选项使用

```
-i	交互式提示
-r	递归拷贝目录及其内容
-v	显示拷贝后的路径描述
-a	保留文件的原有权限
```

# 五、Linux 高级命令

```
>	    如果文件存在会覆盖原有文件内容
>>	    如果文件存在会追加写入文件末尾
cat	    查看小型文件
more	分屏查看大型文件
ln -s	创建软链接
ln	    创建硬链接
grep	文本搜索
find	在指定目录下查找文件(包括目录)
chmod	修改文件权限
        r	可读，权限值是4
        w	可写，权限值是2
        x	可执行，权限值是1
        -	无任何权限，权限值是0
        u	user, 表示该文件的所有者
        g	group, 表示用户组
        o	other, 表示其他用户
        a	all, 表示所有用户

```

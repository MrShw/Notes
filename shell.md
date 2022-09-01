sed -nei '3,5adcpI' words
/key/
/rex/
I:case insensive

sed -n 's/old/new/g' words

sed -n '/[0-9]/p' filename 将文件中匹配数字的行打印出来
sed -n '/[a-z]/p' filename 将文件中匹配小写字母的行打印出来
sed -n '/[A-Z]/p' filename 将文件中匹配大写字母的行打印出来

sed -i '/[0-9]/d' filename 将文件中匹配数字的行删除
sed -n '/[a-z]/d' filename 将文件中匹配小写字母的行删除
sed -n '/[A-Z]/d' filename 将文件中匹配大写字母的行删除

sed -i '/[0-9]/s/root/huoqiu/g' filename 将文件中匹配数字的行里的 root 替换为 huoqiu
sed -i '/[a-z]/s/root/huoqiu/g' filename 将文件中匹配小写字母的行里的 root 替换为 huoqiu
sed -i '/[A-Z]/s/root/huoqiu/g' filename 将文件中匹配大写字母的行里的 root 替换为 huoqiu

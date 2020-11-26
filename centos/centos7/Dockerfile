FROM centos:centos7

### 安装中文环境
# yum -y install kde-l10n-Chinese            安装中文语言包
# yum -y reinstall glibc-common              更新glibc包
# localedef -c -f UTF-8 -i zh_CN zh_CN.utf8  设置系统语言包
# export LC_ALL=zh_CN.UTF-8                  设置环境变量

### 更改时区
# ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 

RUN cd /etc/yum.repos.d \
	&& mv CentOS-Base.repo CentOS-Base.repo.bak \
	&& curl -sSLO http://mirrors.163.com/.help/CentOS7-Base-163.repo \
	&& mv CentOS7-Base-163.repo CentOS-Base.repo \
	&& yum clean all \
	&& yum makecache \
	&& rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-* \
	&& yum -y update \
    && yum -y install deltarpm man vim net-tools kde-l10n-Chinese \
	&& yum -y reinstall glibc-common \
	&& localedef -c -f UTF-8 -i zh_CN zh_CN.utf8 \
	&& ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

ENV LANG zh_CN.UTF-8
ENV LC_ALL zh_CN.UTF-8

CMD ["/bin/bash"]

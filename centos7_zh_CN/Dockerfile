FROM centos:7

RUN set -eux; \
    yum -y install kde-l10n-Chinese telnet;\
    yum -y reinstall glibc-common;\
    yum clean all;\
    localedef -c -f UTF-8 -i zh_CN zh_CN.utf8

ENV LC_ALL=zh_CN.UTF-8
ENV TZ=Asia/Shanghai

CMD ["/bin/bash"]
FROM centos:7
MAINTAINER Andy Neff <andyneff@users.noreply.github.com>

#Docker RUN example, pass in the git-lfs checkout copy you are working with
LABEL RUN="docker run -v git-lfs-repo-dir:/src -v repo_dir:/repo"

COPY test_lfs.bsh /tmp/test_lfs.bsh

CMD yum install -y http://${REPO_HOSTNAME:-git-lfs.github.com}/centos/7/RPMS/noarch/git-lfs-repo-release-1-1.el7.centos.noarch.rpm && \
    yum install -y git-lfs && \
    git-lfs && \
    yum install -y perl-Digest-SHA golang && \
    /tmp/test_lfs.bsh

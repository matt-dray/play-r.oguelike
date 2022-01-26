FROM rocker/binder:4.1.2
LABEL maintainer='Matt Dray'
USER root
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

RUN installGithub.r matt-dray/r.oguelike

RUN wget https://github.com/matt-dray/play-r.oguelike/raw/master/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2021-01-26/')); devtools::install_deps()"

RUN rm DESCRIPTION.1; exit 0


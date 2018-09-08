FROM rtndocker/manifoldcore

WORKDIR /root/Manifold/ManifoldNodes/ManifoldNexus
RUN qmake
RUN make clean
RUN make -j8
RUN make install

WORKDIR /
RUN mkdir -p .config
RUN chmod a+rw .config

ENTRYPOINT ["ManifoldNexus"]
CMD ["-s/.config/Manifold/ManifoldNexus.ini"]






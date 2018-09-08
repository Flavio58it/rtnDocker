FROM rtndocker/manifoldcore

WORKDIR /root/Manifold/ManifoldNodes/ManifoldManager
RUN qmake
RUN make clean
RUN make -j8
RUN make install

WORKDIR /
RUN mkdir -p .config
RUN chmod a+rw .config

ENTRYPOINT ["ManifoldManager"]
CMD ["-s/.config/Manifold/ManifoldManager.ini"]






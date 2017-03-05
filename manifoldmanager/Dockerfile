FROM rtndocker/manifoldcore

WORKDIR /root/Manifold/ManifoldNodes/ManifoldManager
RUN qmake
RUN make clean
RUN make -j8
RUN make install

ENTRYPOINT ["ManifoldManager"]
CMD ["-s/.config/Manifold/ManifoldManager.ini"]






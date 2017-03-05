FROM rtndocker/manifoldcore

WORKDIR /root/Manifold/ManifoldNodes/ManifoldNexus
RUN qmake
RUN make clean
RUN make -j8
RUN make install

ENTRYPOINT ["ManifoldNexus"]
CMD ["-s/.config/Manifold/ManifoldNexus.ini"]






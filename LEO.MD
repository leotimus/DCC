1. dataset for this project is saved at: 
   /share_data/DCC/data/mnist
   one can simply link that with the your project by:
   1. cd to project root 
   2. ln -s /share_data/DCC/data/mnist data/mnist
2. conda profile named: dcc
3. Pretraining SDAE
   1. python pretraining.py --data mnist --tensorboard --id 1 --niter 50000 --lr 10 --step 20000
4. Extracting Pretrained Features
   1. python extract_feature.py --data mnist --net checkpoint_4.pth.tar --features pretrained
5. Copying mkNN graph
   1. python copyGraph.py --data mnist --graph pretrained.mat --features pretrained.pkl --out pretrained
6. Running Deep Continuous Clustering
   1. python DCC.py --data mnist --net checkpoint_4.pth.tar --tensorboard --id 1
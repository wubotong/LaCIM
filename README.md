# LaCIM

1. Simulation
 
 `python lacim_d_num_cluster_3_original_1667.py` to get the results of the second row in Table 1.
 
 `python lacim_d_num_cluster_5.py ` to get the results of the third row in Table 1.

2. Real World (Colored MNIST)

- `python generate_colored_mnist.py --sigma 0.02 --env_num 2 --color_num 2 --env_type 3 --test_ratio 0.1` to generate colored MNIST. The training environment include 0.9 and 0.95. The ratio of testing environment is 0.1.
- `CUDA_VISIBLE_DEVICES=0 python LaCIM_rho.py --epochs 120 --optimizer sgd --lr 0.1 --lr_decay 0.5 --lr_controler 80 --in_channel 3 --batch-size 256 --test-batch-size 256 --reg 0.0002 --beta 1 --dataset mnist --num_classes 2 --env_num 2 --seed -1 --zs_dim 32 --root ./data/colored_MNIST_0.02_env_2_3_c_2_0.10/ --test_ep 50 --lr2 0.0005 --reg2 0.005 --sample_num 10 --image_size 28 --z_ratio 0.5`
- `CUDA_VISIBLE_DEVICES=0 python d_LaCIM.py --epochs 120 --optimizer sgd --lr 0.1 --lr_decay 0.5 --lr_controler 80 --in_channel 3 --batch-size 256 --test-batch-size 256 --reg 0.00005 --dataset mnist --num_classes 2 --env_num 2 --seed -1 --zs_dim 32 --root ./data/colored_MNIST_0.02_env_2_3_c_2_0.10/ --test_ep 50  --lr2 0.02 --reg2 0.05 --sample_num 10 --image_size 28 --alpha 8.0 --gamma 1.0 --beta 1.0 --z_ratio 0.5`  to get the results of ours in Table 3.

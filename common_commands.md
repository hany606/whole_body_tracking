python scripts/csv_to_npz.py --input_file /home/hhamed-iit.local/repos/datasets/LAFAN1_Retargeting_Dataset/g1/dance1_subject2.csv --input_fps 30 --frame_range 122 722 \
    --output_name dance1_subject2 --output_fps 50 --headless

python replay_motion.py --motion_file motions/dance1_subject2.npz --headless

python scripts/rsl_rl/train.py --task=Tracking-Flat-G1-v0 \
--motion_file dance1_subject2.npz \
--headless --logger wandb --log_project_name iit-tmp --run_name dance1_subject2 --max_iterations 2000 --num_envs 8
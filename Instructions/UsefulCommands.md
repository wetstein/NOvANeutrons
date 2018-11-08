setup_nova -b maxopt -r S16-08-24
setup_proxy
srt_setup -a
ifdh cp -r /pnfs/nova/scratch/users/wetstein/test .
echo $SRT_QUAL
echo @SRT_PUBLIC_CONTEXT
echo @SRT_PRIVATE_CONTEXT
submit_nova_art.py -f make_neutron_dists.cfg 
jobsub_q --user=wetstein
jobsub_fetchlog --user=wetstein --jobid=10361332.0@fifebatch1.fnal.gov --unzipdir=temp/
nova -c Demo/tutanajob.fcl /nova/ana/users/wetstein/neardet_r00010727_s03_t00_S15-05-22_v1_data.pid.root 
submit_nova_art.py -f make_neutron_dists_FHC.cfg 
ifdh cp -r /pnfs/nova/scratch/users/wetstein/test .

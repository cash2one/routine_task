�̰�ÿ��������ݵļ������
command: 
	bash -x ./run.sh 20170720 >../log/day_20170720.log 2>&1
	bash -x ./run_day.sh `date -d "1 day ago" +"%Y%m%d"` >../log/day_`date -d "1 day ago" +"%Y%m%d"`.log 2>&1

	nohup bash -x ./run.sh 20170720 >../log/day_20170720.log 2>&1 &
	nohup bash -x ./run_day.sh `date -d "1 day ago" +"%Y%m%d"` >../log/day_`date -d "1 day ago" +"%Y%m%d"`.log 2>&1 &


dataĿ¼�£�
=============================================================================
shangbai_ori�������̰ٵ�ԭʼ���� '\t': userid, url
shangbai_ori.md5��ԭʼ���ݵ�md5�����ļ�

shangbai_data��ԭʼ����Ԥ�������̰����ݣ���Ҫ�ǲ���id��ȥ����Ч����(�ֶδ���)��'\t': id, userid, url
shangbai_data.md5���̰����ݵ�md5�����ļ�

na_input���̰����ݳ�ȡ����url���ݣ���ΪNA������������ '\t': id, url
na_output��NA������������ '\t': id, url, tags, detail_info

check_wisefc_na_day_20170730.res�����ղ��������ݣ����̰ٻ�ȡ '\t': userid, url, check_time, check_type, status
check_wisefc_na_day_20170730.res.md5��md5�����ļ�

pc_dead��pc/�����ʱ� '\t': userid, url
pc_dead.md5��md5�����ļ�

mail_data������ͳ�����ݣ����ڷ����ʼ�


onlineĿ¼�£�
=============================================================================
pc_dead��pc/�����ʱ����ܽ�h���pc/dead���� '\t': userid, url
pc_dead.md5��md5�����ļ�

mixer_full: mixerȫ���δʱ�����pc/dead�ʱ����˵�slp_uid, replace_dict, white_url�������ʱ�����'\t': userid, url, url_sign, 1, 0, 0, 100, 0

mixer_block��mixer�������δʱ���mixer_fullֱ�ӳ�ȡ�������� '\t': url_sign, 1, 0, 0, 100, 0
mixer_block.md5��md5�����ļ�

feed_block��feed���δʱ�����pc/dead�ʱ�ֱ������ '\t': 0, url, 1
feed_block.md5��md5�����ļ�

badcase_dict: pc/dead url���״ʱ�, join replace_dict���� '\t': url_noproto, 0, replace_url
badcase_dict.md5: md5�����ļ�

replace_dict�����״ʱ� '\t': userid, url

white_domain: �����������������ٻ�����url

white_url: url��������update_white_url.sh�ű��ᶨʱ���ܿشʱ���ȡ�����±��ʱ� '\t': url, userid
white_url.md5: md5�����ļ�

slp_dict: slp�ͻ�������update_slp_dict.sh�ű��ᶨʱ���ܿشʱ���ȡ�����±��ʱ� '\t': userid, tradeid, wise_ratio, ...
slp_dict.md5: md5�����ļ�

slp_uid: ���ݸ�������ֱ�Ӵ�slp_dict��ȡ����������Ϊ��tradeid!=0 && wise_ratio>=50 && wise_ratio<=100
slp_uid.md5: md5�����ļ�

mail_template���ʼ�ģ�壬����sendmail�����






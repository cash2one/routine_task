商百每天更新数据的检测任务
command: 
	bash -x ./run.sh 20170720 >../log/day_20170720.log 2>&1
	bash -x ./run_day.sh `date -d "1 day ago" +"%Y%m%d"` >../log/day_`date -d "1 day ago" +"%Y%m%d"`.log 2>&1

	nohup bash -x ./run.sh 20170720 >../log/day_20170720.log 2>&1 &
	nohup bash -x ./run_day.sh `date -d "1 day ago" +"%Y%m%d"` >../log/day_`date -d "1 day ago" +"%Y%m%d"`.log 2>&1 &


data目录下：
=============================================================================
shangbai_ori：就是商百的原始数据 '\t': userid, url
shangbai_ori.md5：原始数据的md5检验文件

shangbai_data：原始数据预处理后的商百数据，主要是补充id和去除无效数据(字段错误)，'\t': id, userid, url
shangbai_data.md5：商百数据的md5检验文件

na_input：商百数据抽取出的url数据，作为NA检测的输入数据 '\t': id, url
na_output：NA检测后的输出数据 '\t': id, url, tags, detail_info

check_wisefc_na_day_20170730.res：最终产出的数据，供商百获取 '\t': userid, url, check_time, check_type, status
check_wisefc_na_day_20170730.res.md5：md5检验文件

pc_dead：pc/死链词表 '\t': userid, url
pc_dead.md5：md5检验文件

mail_data：汇总统计数据，用于发送邮件


online目录下：
=============================================================================
pc_dead：pc/死链词表，汇总近h天的pc/dead数据 '\t': userid, url
pc_dead.md5：md5检验文件

mixer_full: mixer全屏蔽词表，根据pc/dead词表，过滤掉slp_uid, replace_dict, white_url白名单词表，生成'\t': userid, url, url_sign, 1, 0, 0, 100, 0

mixer_block：mixer在线屏蔽词表，从mixer_full直接抽取出的数据 '\t': url_sign, 1, 0, 0, 100, 0
mixer_block.md5：md5检验文件

feed_block：feed屏蔽词表，根据pc/dead词表直接生成 '\t': 0, url, 1
feed_block.md5：md5检验文件

badcase_dict: pc/dead url兜底词表, join replace_dict生成 '\t': url_noproto, 0, replace_url
badcase_dict.md5: md5检验文件

replace_dict：兜底词表 '\t': userid, url

white_domain: 白名单域名，用于召回死链url

white_url: url白名单，update_white_url.sh脚本会定时从总控词表拉取，更新本词表 '\t': url, userid
white_url.md5: md5检验文件

slp_dict: slp客户名单，update_slp_dict.sh脚本会定时从总控词表拉取，更新本词表 '\t': userid, tradeid, wise_ratio, ...
slp_dict.md5: md5检验文件

slp_uid: 根据覆盖条件直接从slp_dict抽取，覆盖条件为：tradeid!=0 && wise_ratio>=50 && wise_ratio<=100
slp_uid.md5: md5检验文件

mail_template：邮件模板，用于sendmail命令发送






def backbone_backup_add(backbone_name):
    if ";" in str(backbone_name):
        backbone_list = str(backbone_name).split(';')
        sum_list = []
        for i in backbone_list:
            if i == "":
                continue
            else:
                if len(get_backbone_info_max(i)) > 0:
                    bw = get_backbone_info_max(i)[0]
                    sum_list.append(bw)
                elif len(get_backbone_info_max(i)) == 0:
                    print(i + '查不到骨干资料')
                    sum_list.append(0)
                else:
                    return str(i+'错误')
        res = sum(sum_list)
        return res
    elif "none" in str(backbone_name):
        return "none"
    elif "office" in str(backbone_name):
        return "none"
    elif "n/a" in str(backbone_name):
        return "none"
    elif "tunnel" in str(backbone_name):
        return "none"
    elif backbone_name == 0:
        return "none"
    else:
        if len(get_backbone_info_max(backbone_name)) > 0:
            bw = int(get_backbone_info_max(backbone_name)[0])
            return bw
        elif len(get_backbone_info_max(backbone_name)) == 0:
            print(backbone_name + '查不到骨干资料')
            return 0

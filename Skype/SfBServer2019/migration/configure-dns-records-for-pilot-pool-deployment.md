---
title: 為試驗集區部署設定 DNS 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 部署試驗集區之前，您必須更新 DNS 主機試驗集區的專案。 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: e77a85d84debadc19e52cb2d195ac86f5b3e6055
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588055"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>為試驗集區部署設定 DNS 記錄

部署試驗集區之前，您必須更新 DNS 主機的試驗集區的專案。 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
  
### <a name="to-configure-dns-host-a-records"></a>設定 DNS 主機 A 記錄

1. 在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。
    
2. 在您網域的主控台樹中，展開 [**正向對應區域**]，然後在將安裝商務用 Skype Server 2019 的網域上按一下滑鼠右鍵。
    
3. 按一下 **[新增主機 (A 或 AAAA)]**。
    
4. 按一下 [**名稱**]，然後輸入商務用 Skype Server 2019 集區的主機名稱 (功能變數名稱會從記錄定義所在的區域中取得，而不需要輸入為 A record) 的一部分。
    
5. 按一下 [ **IP 位址**]，然後輸入前端集區的 ip 位址。
    
6. 按一下 **[新增主機]**，然後按一下 **[確定]**。 
    
7. 完成時，按一下 **[完成]**。
    


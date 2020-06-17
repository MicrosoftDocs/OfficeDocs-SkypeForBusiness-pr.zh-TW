---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753265"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 記錄

若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
  
本主題說明如何在遷移至商務用 Skype Server 2019 後，更新網域名稱系統（DNS）記錄。 在所有使用者移至商務用 Skype Server 2019，但在解除舊版集區或 Director 之前，您必須針對每個 SIP 網域更新內部 DNS 中的 DNS SRV 記錄。 此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。
  
## <a name="to-configure-a-dns-srv-record"></a>設定 DNS SRV 記錄

1. 在 DNS 伺服器上，按一下 [**開始**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。
    
2. 在 SIP 網域的主控台樹中，展開 [**正向對應區域**]，展開安裝商務用 Skype Server 2019 的 SIP 網域，然後流覽至 [ **_tcp** ] 設定。 
    
3. 在右窗格中，以滑鼠右鍵按一下 [ **_sipinternaltls** ]，然後選取 [**屬性**]。
    
4. 在 [**提供這項服務的主機**] 中，將主機 FQDN 更新為指向商務用 Skype Server 2019 集區。
    
5. 按一下 [確定]****。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>確認可解析前端集區或 Standard Edition server 的 FQDN

1. 登入網域中的用戶端電腦。
    
2. 按一下 [開始]****，然後按一下 [執行]****。
    
3. 在 [**開啟**] 方塊中輸入 cmd，然後按一下 **[確定]**。
    
4. 在命令提示字元中輸入 nslookup _\<FQDN of the Front End pool\>_ 或 _\<FQDN of the Standard Edition server\>_ ，然後按 enter 鍵。
    
5. 請確認您收到的回復可解析為 FQDN 的適當 IP 位址。
    


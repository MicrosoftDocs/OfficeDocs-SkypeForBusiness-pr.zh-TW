---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要成功完成此程式, 您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193904"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 記錄

若要成功完成此程式, 您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。
  
本主題說明如何在遷移到商務用 Skype Server 2019 之後, 更新網域名稱系統 (DNS) 記錄。 在所有使用者移至商務用 Skype Server 2019 之後, 但在解除舊版池或主管之前, 您必須在內部 DNS 中更新每個 SIP 網域的 DNS SRV 記錄。 這個程式假設您的內部 DNS 擁有您 SIP 使用者網域的區域。
  
## <a name="to-configure-a-dns-srv-record"></a>若要設定 DNS SRV 記錄

1. 在 DNS 伺服器上, 按一下 [**開始**], 按一下 [**管理工具**], 然後按一下 [ **DNS**]。
    
2. 在您 SIP 網域的 [主控台樹] 中, 展開 [**轉寄查閱區域**], 展開已安裝商務用 Skype Server 2019 的 SIP 網域, 然後流覽至 [ **_tcp** ] 設定。 
    
3. 在右窗格中, 以滑鼠右鍵按一下 [ **_sipinternaltls** ], 然後選取 [**屬性**]。
    
4. 在**提供此服務的主機**中, 更新主機 FQDN 以指向商務用 Skype Server 2019 池。
    
5. 按一下 [確定]****。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>確認可以解析前端池或標準版伺服器的 FQDN

1. 登入網域中的用戶端電腦。
    
2. 按一下 [**開始**], 然後按一下 [**執行**]。
    
3. 在 [**開啟**] 方塊中, 輸入 cmd, 然後按一下 **[確定]**。
    
4. 在命令提示字元中, 輸入_ \<頂層結束池\> _的 nslookup FQDN 或_ \<標準版伺服器\>的 FQDN_, 然後按 enter。
    
5. 確認您收到的回復會解析為適當的 FQDN IP 位址。
    


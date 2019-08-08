---
title: 設定試驗集區部署的 DNS 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在部署試驗池之前, 您必須更新 DNS 主機 A 試驗池的專案。 若要成功完成此程式, 您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: 0de8e144ea8d77e7ffa86562c120a54e3ec61ae0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239660"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>設定試驗集區部署的 DNS 記錄

在部署試驗池之前, 您必須更新 DNS 主機 A 試驗池的專案。 若要成功完成此程式, 您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。
  
### <a name="to-configure-dns-host-a-records"></a>設定 DNS 主機 A 記錄

1. 在 [網域名稱系統 (DNS)] 伺服器上, 按一下 [**開始**], 按一下 [**管理工具**], 然後按一下 [ **DNS**]。
    
2. 在您網域的 [主控台樹] 中, 展開 [**轉寄查閱區域**], 然後以滑鼠右鍵按一下將在其中安裝商務用 Skype Server 2019 的網域。
    
3. 按一下 **[新增主機 (A 或 AAAA)**]。
    
4. 按一下 [**名稱**], 輸入商務用 Skype Server 2019 池的主機名稱 (功能變數名稱是從定義該記錄的區域中假設, 而且不需要輸入為 A 記錄的一部分)。
    
5. 按一下 [ **IP 位址**], 然後輸入前端池的 IP 位址。
    
6. 按一下 [**新增主機**], 然後按一下 **[確定]**。 
    
7. 完成後, 請按一下 [**完成**]。
    


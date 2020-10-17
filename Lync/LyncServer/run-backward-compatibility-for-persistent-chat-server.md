---
title: 對 Persistent Chat Server 執行回溯相容性
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c96b2ad99ce403df32cc224d854c34160bd6c613
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518090"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a>對 Persistent Chat Server 執行回溯相容性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 2013，Persistent Chat Server 端點提供一種方式，來建立指向 Persistent Chat Server 集區的簡單 URL。 這適用于舊版用戶端 (Microsoft Office 通訊伺服器 2007 R2 Group Chat Server 或 Lync Server 2010，群組聊天) 因為使用者可以在手動設定中輸入簡易 URL，以嘗試將舊版用戶端指向執行 Lync 2013 的電腦（持續聊天）。 持續性聊天不會使用此端點，只對舊版用戶端是必要的。 這對可以遷移會議室的過渡期很有用，但是尚未在整個組織中部署 Lync 2013 用戶端。 執行 Lync 2010 Group Chat (用戶端) 的使用者，仍然可以連線到 Persistent Chat Server 後端伺服器。

您不需要建立多個 Persistent 聊天伺服器端點;您只需要每個 Persistent Chat Server 集區的一個。 系統管理員可以建立多個端點 (每個集區一個)，但可將舊版用戶端設定為一次只能連線至一個集區。 在一般或主流案例中，舊版部署只是一個集區。 新的部署通常會將該集區遷移至新的 Lync Server 2013，而且可能會新增額外的其他 Persistent Chat Server 集區。

此主流案例通常會遵循下列模式：

  - 您可以管理具有一個 Lync Server 2010、群組聊天集區和 Lync 2010 群組聊天用戶端的使用者，方法是使用 (預設 sip： ocschat@ \<domainName\> .com 或類似一個) 的一些已知使用者連線到該集區。 使用者 SIP-enabled Active Directory 網域服務，且查閱服務會向其註冊以接收傳入的要求。

  - 接著，您會安裝 Lync Server 2013 Persistent Chat Server 和 Persistent Chat Server 集區。

  - 在使用者通常是離線狀態的期間 (例如週末)：
    
      - 關閉 Lync Server 2010，群組聊天。
    
      - 將資料從 Lync Server 2010，Group Chat 集區遷移至 Lync Server 2013 Persistent Chat Server 集區。
    
      - 從 Active Directory 網域服務中刪除眾所周知的使用者。
    
      - 利用與先前刪除之已知使用者相同的 SIP URI 來建立新的「舊版端點」**。
    
      - 啟動 Lync Server 2013，Persistent Chat server。

  - 使用者可以使用其 Lync 2010 群組聊天 (用戶端) 重新登入，並連接至其資料，而不需要變更任何設定。

  - 您可以在稍後解除委任 Lync Server 2010，群組聊天。 接著，您可以部署 Lync Server 2013、Persistent Chat Server，並安裝新的 Lync Server 2013 Persistent Chat Server 集區。

如需從 Lync Server 2010 （Group Chat to Lync Server 2013，Persistent Chat Server）進行遷移的詳細資訊，請參閱 [從 Lync server 2010 遷移，Group chat 或 Office 通訊伺服器 2007 R2 Group chat To Lync server 2013，Persistent Chat server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

若要執行回溯相容性 (以建立一個指向 Persistent Chat Server 集區的持久聊天伺服器端點，可供舊版群組聊天集區用戶端使用) ：

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

接下來，設定 Persistent Chat 用戶端使用該 SIP 位址作為其連絡人物件。 使用特定 Persistent Chat Server 集區的 **New-CsPersistentChatEndpoint** Cmdlet 來建立 SIP 位址。

若要使用 Windows PowerShell 命令列介面新增 Persistent Chat Server 端點，請考慮下列範例。 在此案例中，您是在 "contoso.com"  拓撲上設定連絡人物件，並將它命名為 "persistentchat"，其中集區的完整網域名稱 (FQDN) 為 "pcpool.contoso.com"：

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>另請參閱


[從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 針對常設聊天室伺服器執行回溯相容性
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>針對常設聊天室伺服器執行回溯相容性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 2013，持續聊天伺服器端點提供一種方式來建立指向持續聊天伺服器池的簡單 URL。 這適用于舊版用戶端（Microsoft Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync Server 2010、群組聊天），因為當您嘗試將舊版用戶端指向執行 Lync 2013 的電腦時，使用者可以在手動設定中輸入簡單的 URL。持續聊天。 此端點不會用於持續聊天，且僅適用于舊版用戶端。 這適用于可遷移會議室的間歇期間，但尚未在整個組織中部署 Lync 2013 用戶端。 執行 Lync 2010 群組聊天（用戶端）的使用者仍然可以連線到持續聊天伺服器後端伺服器。

您不需要建立多個持續聊天伺服器端點;您只需要每個持續聊天伺服器池的一個。 系統管理員可以建立多個端點（每個池一個），但舊用戶端可以設定為一次只連線到一個池。 在一般或主流案例中，舊版部署只是一個池。 新的部署通常會將該池遷移至新的 Lync Server 2013，並且可能會新增其他額外的持久聊天伺服器池。

這個主要案例通常遵循下列模式：

  - 您可以使用一個 Lync Server 2010、群組聊天池及您的 Lync 2010 群組聊天用戶端連線至該池子，方法是使用一些知名使用者（預設 sip： ocschat@\<domainName\>或類似的使用者）連線到該池。 使用者是啟用 SIP 的 Active Directory 網域服務，且查閱服務會使用它們登錄來接收傳入的要求。

  - 接著，您會安裝 Lync Server 2013 永久聊天伺服器與持續聊天伺服器池。

  - 在使用者一般離線時（例如，週末）：
    
      - 關閉 Lync Server 2010、群組聊天。
    
      - 將資料從 Lync Server 2010、群組聊天池遷移至 Lync Server 2013 持續聊天伺服器池。
    
      - 從 Active Directory 網域服務刪除已知的使用者。
    
      - 建立新的*舊版端點*，其 SIP URI 與先前刪除的知名使用者相同。
    
      - 啟動 Lync Server 2013、持久聊天伺服器。

  - 使用者使用其 Lync 2010 群組聊天（用戶端）重新登入，並聯機至其資料，而不需要變更任何設定。

  - 您可以在日後解除 Lync Server 2010、群組聊天。 接著，您可以部署 Lync Server 2013、持續聊天伺服器，以及安裝新的 Lync Server 2013 永久聊天伺服器池。

如需從 Lync Server 2010 遷移的詳細資料，群組聊天至 Lync Server 2013，持續聊天伺服器，請參閱[從 Lync server 2010 遷移、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013，持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

若要執行向後相容性（以建立指向持久聊天伺服器池的永久性聊天伺服器端點，可供舊版群組聊天池用戶端使用）：

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

接著，設定持久聊天用戶端，將該 SIP 位址當作其連絡人物件使用。 SIP 位址是針對特定持久性聊天伺服器池中的**新-CsPersistentChatEndpoint** Cmdlet 建立的。

若要使用 Windows PowerShell 命令列介面新增持續聊天伺服器端點，請考慮下列範例。 在這種情況下，您是將連絡人物件設定為「contoso.com」拓撲中的「persistentchat」，其中池的完整功能變數名稱（FQDN）是「pcpool.contoso.com」：

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>請參閱


[從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


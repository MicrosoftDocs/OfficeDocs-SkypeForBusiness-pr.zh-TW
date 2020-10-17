---
title: Lync Server 2013：為封鎖的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be998071bc0cad49d3e96c3c82cf395b2da7ca1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515680"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中為封鎖的外部網域設定支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

如果您已設定同盟協力廠商的支援，可以管理要禁止哪些網域與您的組織建立同盟。 如果您啟用此選項，封鎖網域清單將作為封鎖清單 (不被允許的明確項目清單)，並套用於同盟網域探索中。 如需詳細資訊，請參閱 [啟用或停用 Lync Server 2013 中的同盟](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)協力廠商探索。

封鎖一個或多個外部網域，不讓它們連線至您的組織。若要這樣做，請將網域新增至封鎖網域清單。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>將外部網域新增至封鎖網域清單

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[外部使用者存取]**。

4.  依序按一下 **[同盟網域]**、**[新增]** 和 **[封鎖網域]**。

5.  在 **[新增同盟網域] ** 中，執行下列動作：
    
      - 在 **[網域名稱 (或 FQDN)]** 中，輸入您要封鎖的同盟協力廠商網域名稱。
        
        <div>
        

        > [!NOTE]  
        > 名稱長度不可超過 256 個字元。<BR>搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 <STRONG>contoso.com</STRONG>，搜尋也會傳回網域 <STRONG>it.contoso.com</STRONG>。<BR>不能同時封鎖又允許同一個同盟協力廠商網域。 Lync Server 2013 避免發生這種情況，因此您不需要同步處理清單。

        
        </div>
    
      - (選用) 在 **[註解]** 中，輸入您想與其他系統管理員分享的此設定相關資訊。

6.  按一下 **[認可]**。

7.  為您要封鎖的每個同盟協力廠商重複步驟 4 到 6。

若要啟用同盟使用者存取，您也必須在組織中啟用同盟使用者存取支援。 如需詳細資訊，請參閱 [Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


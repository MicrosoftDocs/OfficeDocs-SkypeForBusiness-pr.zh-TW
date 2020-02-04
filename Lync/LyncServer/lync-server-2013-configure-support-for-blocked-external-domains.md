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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中為封鎖的外部網域設定支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

如果您已設定聯盟夥伴的支援，您可以管理哪些網域將被封鎖，無法與您的組織進行聯盟。 封鎖的網域清單會充當封鎖清單（不允許的明確專案清單），如果您已啟用此選項，就會套用到聯盟網域探索中。 如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的同盟合作夥伴探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。

封鎖一或多個外部網域以連線到您的組織。 若要這樣做，請將網域新增到封鎖網域的清單中。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>將外部網域新增至封鎖的網域清單

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]。

4.  按一下 [**聯盟網域**]，按一下 [**新增**]，然後按一下 [**封鎖的網域**]。

5.  在**新的聯盟網域**中，請執行下列動作：
    
      - 在 **[Domain name （或 FQDN）**] 中，輸入您要封鎖的聯盟夥伴網域的名稱。
        
        <div>
        

        > [!NOTE]  
        > 名稱長度不能超過256個字元。<BR>在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。 例如，如果您輸入<STRONG>contoso.com</STRONG>，則搜尋也會傳回網域<STRONG>it.contoso.com</STRONG>。<BR>聯盟夥伴網域不能同時封鎖及允許。 Lync Server 2013 避免發生這種情況，因此您不需要同步處理您的清單。

        
        </div>
    
      - 可選在 [**批註**] 中，輸入您要與其他系統管理員共用這項設定的資訊。

6.  按一下 [認可]****。

7.  針對您要封鎖的每個聯盟夥伴，重複步驟4到6。

若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。 如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


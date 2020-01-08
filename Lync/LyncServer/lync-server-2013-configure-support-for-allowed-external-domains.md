---
title: Lync Server 2013：針對允許的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中針對允許的外部網域設定支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

如果您已設定聯盟夥伴的支援，您可以管理哪些特定網域可以與您的組織聯盟。 您將一或多個特定外部網域設定為允許聯盟網域。 若要這樣做，請將每個網域新增到允許的網域清單中。 即使您的組織已啟用合作夥伴探索，如果網域是聯盟夥伴，可能需要與超過1000的使用者通訊，或者可能需要每秒傳送超過20封郵件。 如果您的組織未啟用合作夥伴探索，則只有您新增至 [允許的網域] 清單的外部網域使用者，才能與組織中的使用者參與 IM 和會議。 如果您想要將同盟網域的存取許可權制為執行同盟夥伴之存取邊緣服務的特定伺服器，您可以在允許的網域清單中，為每個網域指定執行 Access Edge 服務的伺服器功能變數名稱。

<div>


> [!NOTE]  
> 此程式說明如何針對特定網域設定支援，但實現同盟使用者的支援也需要您針對貴組織啟用聯盟使用者支援，以及設定及套用原則，以控制哪些使用者可以與聯盟使用者共同作業。 如需啟用聯盟使用者支援的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</A>。 如需設定控制同盟的原則的詳細資料，請參閱<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制聯盟使用者存取權的原則</A>。



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>將外部網域新增至允許的網域清單

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**聯盟網域**]。

4.  在 [**聯盟網域**] 頁面上，按一下 [**新增**]，然後按一下 [**允許的網域**]。

5.  在**新的聯盟網域**中，請執行下列動作：
    
      - 在 **[Domain name （或 FQDN）**] 中，輸入聯盟夥伴網域的名稱。
        
        <div>
        

        > [!NOTE]  
        > 這個名稱必須是唯一的，而且不能作為執行存取邊緣服務的此伺服器的允許網域存在。 名稱長度不能超過256個字元。<BR>在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。 例如，如果您輸入<STRONG>contoso.com</STRONG>，則搜尋也會傳回網域<STRONG>it.contoso.com</STRONG>。<BR>聯盟夥伴網域不能同時封鎖及允許。 Lync Server 2013 避免發生這種情況，因此您不需要同步處理您的清單。

        
        </div>
    
      - 如果您想要將此聯盟網域的存取許可權制為執行存取邊緣服務的特定伺服器的使用者，請在 **[存取邊緣服務（FQDN）**] 中，輸入執行 [存取邊緣] 服務之聯盟網域伺服器的 FQDN。
    
      - 如果您想要提供其他資訊，請在 [**批註**] 中，輸入您要與其他系統管理員共用此設定的資訊。

6.  按一下 [認可]****。

7.  針對您要允許的每個聯盟夥伴網域，重複步驟4到6。

若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。 如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


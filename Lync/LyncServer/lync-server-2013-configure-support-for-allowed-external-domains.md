---
title: Lync Server 2013：針對允許的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eaa9da579561464c46776662cacaca80dafe016
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517680"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中為允許的外部網域設定支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

如果已設定對同盟協力廠商的支援，則可以管理哪些特定網域可以與您的組織進行同盟。設定一個或多個特定的外部網域作為允許的同盟網域。若要這樣做，請將每個所需網域新增至允許網域清單。如果網域是可能需要與您超過 1,000 位使用者通訊或每秒傳送超過 20 封訊息的同盟協力廠商，則即使您的組織已啟用協力廠商探索，也建議您這樣做。如果您的組織未啟用協力廠商探索，則只有已新增至允許網域清單的外部網域的使用者，才能和您組織內的使用者進行 IM 和會議通訊。如果您要將同盟網域的存取限制於同盟協力廠商執行 Access Edge Service 的特定伺服器，可以針對允許網域清單中的每個網域，指定執行 Access Edge Service 之伺服器的網域名稱。

<div>


> [!NOTE]  
> 此程序說明如何設定特定網域的支援，但實作同盟使用者的支援還需要您的組織啟用同盟使用者的支援，以及設定和套用原則以控制哪些使用者可以與同盟使用者共同作業。 如需啟用同盟使用者支援的詳細資訊，請參閱 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access In Lync Server 2013</A>。 如需設定控制同盟之原則的詳細資訊，請參閱 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</A>。



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>若要將外部網域新增至允許網域清單

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[同盟網域]**。

4.  在 **[同盟網域]** 頁面上，依序按一下 **[新增]** 和 **[允許的網域]**。

5.  在 **[新增同盟網域]** 中，執行下列動作：
    
      - 在 **[網域名稱 (或 FQDN)]** 中，輸入同盟協力廠商網域的名稱。
        
        <div>
        

        > [!NOTE]  
        > 此名稱必須是唯一的，而且不能已存在作為這個執行 Access Edge Service 的伺服器的允許網域。此外，名稱長度不可超過 256 個字元。<BR>搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 <STRONG>contoso.com</STRONG>，搜尋也會傳回網域 <STRONG>it.contoso.com</STRONG>。<BR>不能同時封鎖又允許同一個同盟協力廠商網域。 Lync Server 2013 避免發生這種情況，因此您不需要同步處理清單。

        
        </div>
    
      - 如果您要將同盟網域的存取限制於執行 Access Edge Service 之特定伺服器的使用者，可以在 **[Access Edge Service (FQDN)]** 中輸入執行 Access Edge Service 之同盟網域伺服器的 FQDN。
    
      - 如果您要提供其他資訊，請在 **[註解]** 中輸入您想與其他系統管理員分享有關此設定的資訊。

6.  按一下 **[認可]**。

7.  為您要允許的每個同盟協力廠商網域重複步驟 4 到 6。

若要啟用同盟使用者存取，您也必須在組織中啟用對同盟使用者存取的支援。 如需詳細資訊，請參閱 [Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


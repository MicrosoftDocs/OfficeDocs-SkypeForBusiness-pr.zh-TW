---
title: Lync Server 2013：管理組織的外部存取原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afc2b1599551cfc3b7ee7341e441946610166ba0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>在 Lync Server 2013 中管理外部存取原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。

依預設，不會將任何原則設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已經為組織啟用外部使用者存取支援也一樣。若要控制外部使用者存取的使用，您必須設定一或多個原則，並為每個原則指定支援的外部使用者存取類型。您可以使用下列原則範圍來進行建立和設定。預設會建立全域原則，但無法加以刪除。

  - **全域原則**   全域原則是在您部署 Edge Server 時建立。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個類型的外部使用者存取選項。 全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，不會將它移除。 而是會將它重設為預設值。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者對特定網站存取的支援。 網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。 根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立並設定一或多個使用者原則，以限制遠端使用者對特定網站存取的支援。 使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。 例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。 如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。

<div>


> [!IMPORTANT]  
> 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則（影響最大）會覆寫網站原則，然後網站原則會覆寫全域原則（影響最小）。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。



</div>

這些選項包括下列類型的外部存取：

  - **啟用與同盟使用者的通訊**   如果您想要支援使用者對同盟合作夥伴網域的存取，請啟用此選項。 此設定會設定使用者與其他 SIP 同盟網域通訊的能力，以及託管的提供者，如 Microsoft 365。 選取此設定可讓您選取允許與 XMPP 同盟網域進行通訊的選項。
    
    做為選項，如果您先選取 **[啟用與同盟使用者的通訊]**，則可選取 **[啟用與 XMPP 同盟協力廠商的通訊]**。XMPP 同盟是與使用 Extensible Messaging and Presence Protocol (XMPP) 的組織同盟。
    
    <div>
    

    > [!NOTE]  
    > 如果您啟用 XMPP 同盟，您也必須在拓撲產生器的 [Edge 集區] 設定區段中，選取 [部署<STRONG>XMPP 同盟</STRONG>]。 針對 XMPP 同盟進行設定會在 Edge Server 上部署 XMPP Proxy，並在前端伺服器上部署 XMPP 閘道。

    
    </div>

  - **啟用與遠端使用者**     的通訊如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以透過網際網路連線至 Lync Server，請啟用此選項。

  - **啟用與公用使用者**     的通訊如果您希望內部使用者能夠與公用 IM 提供者連絡人（如 Windows Live、Yahoo \! 和北美線上（AOL）等）進行通訊，請啟用此選項。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公開 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
    > <LI>
    > <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 除了啟用外部使用者存取支援，您還必須設定相關原則以控制組織外部使用者存取的使用，接著再為使用者提供任何類型的外部使用者存取。 如需建立、設定及套用外部使用者存取原則的詳細資訊，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access In Lync Server 2013</A>。



</div>

**使用 Windows PowerShell Cmdlet 來檢視外部存取原則**

  - 您可以使用 Lync Server 管理命令介面和**Get-CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    若要檢視關於您所有外部存取原則的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsExternalAccessPolicy
    
    此命令會傳回與下列相似的資訊：
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [在 Lync Server 2013 中設定控制遠端使用者存取的原則](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中設定原則以控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [在 Lync Server 2013 中重設或刪除外部使用者存取原則](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


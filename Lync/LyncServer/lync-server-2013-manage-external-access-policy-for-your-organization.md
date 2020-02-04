---
title: Lync Server 2013：管理組織的外部使用存取原則
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
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>在 Lync Server 2013 中管理外部使用存取原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。

根據預設，沒有任何原則可設定支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。 若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。 下列原則作用中可供建立及設定。 根據預設，會建立全域原則，但無法刪除。

  - **全域原則**   當您部署邊緣伺服器時，就會建立全域原則。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。 全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，就不會將它移除。 相反地，您可以將其重設為預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。 網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。 根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。 使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。 例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。 如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。

<div>


> [!IMPORTANT]  
> 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。



</div>

這些選項包括下列外部存取類型：

  - ****    如果您想要支援使用者存取聯盟夥伴網域，請啟用與同盟使用者進行通訊。 此設定會設定使用者與其他 SIP 聯盟網域通訊的能力，以及 Microsoft Office 365 等主機提供者。 選取此設定可讓您選取允許與 XMPP 聯盟網域進行通訊的選項。
    
    如果您先選取 [**啟用與聯盟使用者的通訊**]，您可以選取 [**啟用與 XMPP 聯盟夥伴的通訊**] 作為選項。 XMPP 同盟是與使用可擴展訊息和目前狀態通訊協定（XMPP）的組織進行同盟。
    
    <div>
    

    > [!NOTE]  
    > 如果您啟用 XMPP 同盟，您也必須在拓撲建立器的 [Edge 池設定] 區段中，選取以部署<STRONG>XMPP 同盟</STRONG>。 針對 XMPP 同盟進行設定，在 Edge 伺服器上部署 XMPP Proxy，並在前端伺服器上部署 XMPP 閘道。

    
    </div>

  - ****    如果您想要在您的組織外的使用者（例如出差的遠端電腦）連線至 Lync Server，可以透過網際網路連線到遠端使用者，請啟用此選項。

  - ****    如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊（例如 Windows Live、Yahoo\!和美洲 Online （AOL）），請啟用此選項，以便與公用使用者進行通訊。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
    > <LI>
    > <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 除了啟用外部使用者存取支援之外，您也必須先設定原則，以控制在您的組織中使用外部使用者存取權，才能供使用者使用任何類型的外部使用者存取。 如需有關建立、設定及套用外部使用者存取原則的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。



</div>

**使用 Windows PowerShell Cmdlet 來查看外部存取原則**

  - 您可以使用 Lync Server 管理命令介面和**CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看所有外部存取原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsExternalAccessPolicy
    
    這個命令會傳回如下所示的資訊：
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [在 Lync Server 2013 中設定原則以控制遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中設定原則以控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [在 Lync Server 2013 中重設或刪除外部使用者存取原則](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


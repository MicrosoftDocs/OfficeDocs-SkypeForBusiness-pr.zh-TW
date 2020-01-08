---
title: Lync Server 2013：設定外部使用者存取支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f10e266674d102b25753aeb58c89a365e7bb8e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定外部使用者存取支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

部署 Edge 伺服器或 Edge 池是支援外部使用者的第一個步驟。 如需有關部署邊緣伺服器的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。 原則設定的重要考慮是瞭解原則的優先順序，以及如何套用原則。 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。

完成邊緣伺服器或邊緣池的設定之後，您必須啟用您想要提供的外部使用者存取類型，並設定外部存取的設定。 在 Lync Server 2013 中，您可以使用 Lync Server [控制台]、[Lync Server 管理命令介面] 或這兩者（根據任務需求）來啟用及設定外部使用者存取與原則。

若要支援外部使用者存取，您必須執行下列兩項動作：

  - **啟用貴組織**   的支援：若要在您的部署中啟用外部使用者存取支援，您可以啟用您想要支援的每一種外部存取類型。 您可以在 Lync Server [控制台] 的 [**同盟及外部存取**] 群組中，編輯 [全域設定] 或 [在**外部存取原則**] 頁面上，或使用 lync server 管理命令介面和相關聯的 Cmdlet，來啟用和停用外部使用者存取的支援。 在[Lync Server 2013 的 [聯盟及外部存取 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)] 主題中，可找到管理**外部存取原則**的 Cmdlet。 啟用外部存取的支援指定您的伺服器執行 Lync Server Access Edge 服務支援與外部使用者和伺服器進行通訊。 內部和外部使用者在停用外部使用者存取，或策略尚未設定為支援時，無法進行通訊。

  - **設定並指派一或多個原則**   以支援外部使用者存取，您可以設定原則，以滿足包括下列各項需求：
    
      - ****    使用網站或使用者範圍建立的外部存取原則（預設會存在全域原則，且沒有啟用的設定）。 您可以建立並設定原則，以控制一或多個外部使用者存取類型的使用，包括聯盟使用者存取（包括（如果已選取、聯盟 XMPP 網域）遠端使用者的存取權，以及支援的公用 IM 服務提供者。 您可以在 [**同盟及外部存取**] 群組中的 [**外部存取原則**] 頁面上，使用 [全域原則] 或一或多個管理性建立的網站和使用者原則，在 Lync Server [控制台] 中設定外部原則。 無法刪除全域原則。 您可以建立並設定任何您想要用來限制外部使用者存取特定網站或使用者的網站和使用者原則。 系統會自動指派全域及網站原則。 如果您建立並設定使用者原則，您必須接著使用 [**使用者**] 頁面上的 [Lync Server 控制台] 中的 [使用者設定] 頁面，將它指派給特定的使用者。 尋找您想要此原則套用的使用者或使用者，並指派原則。 您想要將它套用到哪個物件。 若要將已設定的使用者原則指派給使用者，請參閱[在 Lync Server 2013 中將外部使用者存取原則指派給 lync 啟用的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。 每個外部使用者存取原則都可以支援下列一或多項：遠端使用者存取、SIP 同盟使用者存取、XMPP 聯盟使用者存取及公用 IM 連線。
    
      - ****    您建立並設定您組織中的會議的會議原則，包括貴組織中的哪些使用者可以邀請匿名使用者加入他們所託管的會議。 在 Lync Server [控制台 **會議**] 頁面上的 [全域]、[網站] 和 [使用者] 範圍中，控制實際會議設定的原則設定。 如需詳細資訊，請參閱[在 Lync Server 2013 中管理會議與會議](lync-server-2013-managing-meetings-and-conferences.md)。 您可以在 [**存取邊緣**設定] 頁面上，為會議、遠端使用者和聯盟使用者啟用匿名使用者。 **存取邊緣**設定上的原則是全域在範圍中。 沒有可定義網站或使用者原則的選項。 範圍是透過使用全域、網站或使用者原則設定，在 [**外部存取原則**] 頁面上加以控制。
        
        例如，如果您想要允許使用者建立、邀請及管理遠端使用者的會議，您必須在**外部存取原則**全域、網站或使用者原則上設定 [**啟用與遠端使用者的通訊**]，然後在 [**存取邊緣**設定] 頁面上，**啟用與遠端使用者的通訊**。 同樣地，若要允許擁有已定義關聯（例如設定的同盟 SIP 網域和提供者（例如，XMPP federation）不支援會議的匿名使用者或聯盟夥伴的會議，您可以設定 [**啟用與公用使用者的通訊**]，並在**外部存取策略**全域、網站或使用者原則中**與同盟使用者進行通訊**。 接著，您可以在 [**存取邊緣**設定] 頁面上，選取 [**讓匿名使用者存取會議**並**啟用聯盟及公用 IM**連線]。

您可以設定外部使用者存取設定，包括任何您想要用來控制外部使用者存取權的原則，即使您的組織未啟用外部使用者存取權也一樣。 不過，您設定的原則和其他設定只有在您的組織啟用外部使用者存取後才會生效。 外部使用者在停用外部使用者存取權，或未設定外部使用者存取原則支援時，無法與貴組織的使用者進行通訊。

Edge 部署會驗證外部使用者的類型（匿名使用者除外，其由會議 ID 驗證，以及當您建立會議與邀請參與者時傳送給匿名參與者的密碼）。根據您設定 edge 支援的方式來存取。 若要控制通訊，您可以設定一或多個原則，並設定定義您的部署內部和外部的使用者之間相互通訊方式的設定。 [原則與設定] 包含外部使用者存取的預設全域原則，除了您可以建立並設定以啟用一或多種類型的外部使用者存取特定網站或使用者的網站和使用者原則之外。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定原則以控制遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中啟用或停用遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中啟用或停用匿名使用者存取](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中指派會議原則以支援匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定外部使用者存取的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56c8c576c15d9f22add0f81c115c44e72a0c0234
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507500"
---
# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定外部使用者存取的支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。 如需部署 Edge Server 的詳細資訊，請參閱部署檔中的部署 [Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md) 。 設定原則的重要考慮是瞭解原則的優先順序及原則的套用方式。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

完成 Edge Server 或 Edge 集區的設定之後，您必須啟用您要提供的外部使用者存取類型，並設定外部存取的設定。 在 Lync Server 2013 中，您可以根據任務需求，使用 Lync Server 控制台、Lync Server 管理命令介面或兩者來啟用及設定外部使用者存取和原則。

若要支援外部使用者存取，您必須執行下列兩項操作：

  - **為您的組織**     啟用支援若要在部署中啟用外部使用者存取的支援，請啟用每一種您想要支援的外部存取類型。 您可以在 Lync Server 控制台的 [**同盟和外部存取**] 群組或使用 Lync Server 管理命令介面和相關的 Cmdlet，在 [**外部存取原則**] 頁面上編輯全域設定或建立及設定網站或使用者原則，以啟用及停用外部使用者存取的支援。 在[Lync Server 2013 的主題同盟和外部訪問 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)中，會找到用於管理**外部存取原則**的指令程式。 啟用對外部存取的支援指定執行 Lync Server Access Edge service 的伺服器可支援與外部使用者和伺服器的通訊。 內部和外部使用者無法在外部使用者存取遭到停用時或尚未設定原則來支援時進行通訊。

  - **設定並指派一或多個原則**    若要支援外部使用者存取，您必須設定原則，以滿足下列條件：
    
      - **外部存取原則**    以網站或使用者範圍建立 (預設會存在全域原則，且沒有任何已啟用的設定) 。 您可以建立及設定原則，以控制使用一或多種類型的外部使用者存取，包括，同盟使用者存取 (包括（選取）、同盟 XMPP 網域) 遠端使用者使用者存取，以及支援的公用 IM 服務提供者。 在 [**同盟和外部存取**] 群組中的 [**外部存取原則**] 頁面上，使用全域原則或一或多個管理建立的網站和使用者原則，在 Lync Server 控制台中設定外部原則。 全域原則無法刪除。 您可以建立及設定任何網站和使用者原則，您想要用來限制特定網站或使用者的外部使用者存取。 系統會自動指派全域及網站原則。 如果您建立及設定使用者原則，則必須使用 [ **使用者** ] 頁面上 [Lync Server 控制台] 中的 [使用者設定] 頁面，將其指派給特定使用者。 尋找要套用此原則的使用者或使用者，並指派原則。 您想要套用的目標。 若要將設定的使用者原則指派給使用者，請參閱 [將外部使用者存取原則指派給 Lync Server 2013 中啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。 每個外部使用者存取原則都可以支援下列一或多個專案：遠端使用者存取、SIP 同盟使用者存取、XMPP 同盟使用者存取和公用 IM 連線。
    
      - **會議原則**    您可以建立及設定原則，以控制組織中的會議，包括組織中的哪些使用者可以邀請匿名使用者加入其所主持的會議。 在 [Lync Server 控制台 **會議** ] 頁面上，是可控制實際會議設定的全域、網站及使用者範圍中的原則設定。 如需詳細資訊，請參閱 [在 Lync Server 2013 中管理會議和會議](lync-server-2013-managing-meetings-and-conferences.md)。 您可以在 [ **Access Edge** 設定] 頁面上為會議、遠端使用者和同盟使用者啟用匿名使用者。 **Access Edge**設定上的原則為全域範圍。 沒有可定義網站或使用者原則的選項。 範圍是透過使用全域、網站或使用者原則設定，在 [ **外部存取原則** ] 頁面上加以控制。
        
        例如，如果您想要允許使用者以遠端使用者建立、邀請和管理會議，您必須在 [**外部存取原則**全域]、[網站] 或 [使用者] 原則上設定 [**啟用與遠端使用者的通訊**]，並在 [ **Access Edge**設定] 頁面上**啟用與遠端使用者的通訊**。 同樣地，若要讓使用匿名使用者或同盟協力廠商的會議具有定義與 (（如已設定同盟 SIP 網域與提供者）的關聯性（如已設定的同盟 SIP 網域和提供者），XMPP 同盟不支援會議) ，您可以設定 [ **啟用與公用使用者的通訊** ] **，並在** [ **外部存取原則** 全域、網站或使用者 然後，選取 [未補充的全域原則設定]，**可讓匿名使用者存取會議**，並在 [**存取 Edge**設定] 頁面上**啟用同盟和公用 IM 連線能力**。

您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。

您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定控制遠端使用者存取的原則](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中啟用或停用遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中啟用或停用匿名使用者存取](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中指派會議原則以支援匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


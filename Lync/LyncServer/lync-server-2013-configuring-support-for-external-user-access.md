---
title: Lync Server 2013： 設定外部使用者存取的支援
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
ms.openlocfilehash: 94250ec0fbae3a7077e545eebdc848db3c370d19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定外部使用者存取的支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。 如需部署 Edge Server 的詳細資訊，請參閱部署文件中的[Deploying Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。 設定原則的考量重點在於了解原則和如何套用原則的優先順序。 Lync Server 在一個原則層級套用的原則設定可以覆寫其他原則層級套用的設定。 Lync Server 原則的優先順序為: （影響最大） 的使用者原則會覆寫網站原則，並再網站原則會覆寫全域原則 （最低影響）。 這表示接近的原則設定為，這個物件會影響到該原則，它具有物件的多個影響。

完成 Edge Server 或 Edge 集區的安裝後，您必須啟用的一種外部使用者存取您要提供，並設定外部存取的設定。 在 Lync Server 2013 中，啟用及設定外部使用者存取和使用 Lync Server Control Panel、 Lync Server 管理命令介面或兩者的原則工作需求為基礎。

若要支援外部使用者存取，您必須執行下列兩項動作：

  - **啟用支援的組織**   若要啟用支援的部署中的外部使用者存取，您可以啟用每一種要支援的外部存取。 您啟用及停用的編輯全域設定或建立和設定網站或使用者原則上或 Lync Server 控制台的 [**同盟和外部存取**] 群組中的 [**外部存取原則**] 頁面上使用 Lync Server 管理命令介面和相關聯的指令程式支援外部使用者存取。 [同盟和外部存取 cmdlet，在 Lync Server 2013 中](https://docs.microsoft.com/powershell/module/skype/)的主題中找到 Cmdlet 來管理**外部存取原則**。 啟用外部存取的支援，會指定您執行 Lync Server Access Edge service 的伺服器支援與外部使用者與伺服器通訊。 內部與外部使用者無法進行通訊時停用外部使用者存取，或原則有尚未設定為支援它。

  - **設定並指派一或多個原則**   若要支援外部使用者存取，您可以設定原則以滿足需求，包括：
    
      - **外部存取原則**   建立網站或使用者範圍 （全域原則預設會存在，且沒有啟用的設定）。 建立並設定原則以控制的一或多個類型的外部使用者存取，包括，同盟的使用者存取 （包括，如果選取，同盟的 XMPP 網域） 使用遠端使用者的使用者存取權和支援的公用 IM 服務提供者。 您使用的全域原則或一或多個行政規定必須建立的網站與使用者原則，在 [**同盟和外部存取**] 群組中的**外部存取原則**] 頁面上的 Lync Server Control Panel 中設定外部的原則。 全域原則無法刪除。 您建立及設定您想要用來限制對特定網站或使用者的外部使用者存取任何網站與使用者原則。 自動指派全域與網站原則。 如果您建立及設定使用者原則，您必須再將其指派給特定使用者使用 Lync Server 控制台，在 [**使用者**] 頁面上的 [使用者設定] 頁面。 尋找您想要套用至將原則指派此原則的使用者。 您想要套用。 若要設定的使用者原則指派給使用者，請參閱[指派給 Lync Server 2013 中啟用 Lync 功能之使用者的外部使用者存取原則](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。 每個外部使用者存取原則可支援一或多個項目： 遠端使用者存取，SIP 同盟使用者存取、 XMPP 同盟使用者存取和公用 IM 連線。
    
      - **會議原則**   建立並設定原則以控制您的組織，包括您組織中的哪些使用者可以邀請匿名使用者加入他們所主控的會議中的會議。 在 [Lync Server Control Panel **會議**] 頁面會在全域、 網站與使用者範圍的原則設定可控制的實際的會議設定。 如需詳細資訊，請參閱[Managing 會議和 Lync Server 2013 中的會議](lync-server-2013-managing-meetings-and-conferences.md)。 讓匿名使用者在會議、 遠端使用者和在 [ **Access Edge 設定**] 頁面上的同盟的使用者。 **Access Edge 設定**原則是全域範圍中。 沒有定義網站或使用者原則的選項。 範圍被控制的**外部存取原則**] 頁面上，透過全域、 網站或使用者原則設定。
        
        例如，如果您想要允許使用者建立、 邀請和管理會議與遠端使用者，您必須**啟用與遠端使用者的通訊**上設定**外部存取原則**全域、 網站或使用者原則，並**啟用與遠端使用者的通訊** **Access Edge 設定**] 頁面上。 同樣地，若要允許會議與匿名使用者或同盟協力廠商，您必須具有的定義關聯性 （例如設定同盟的 SIP 網域和提供者 – XMPP 同盟不支援會議），在**外部存取原則**全域、 網站或使用者原則設定**啟用與公用使用者的通訊**，並**啟用與同盟使用者的通訊**。 然後選取 [ **Access Edge 設定**」 頁面上**啟用會議的匿名使用者存取**，並**啟用同盟和公用 IM 連線**的附贈全域原則設定。

您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。

您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定原則以控制在 Lync Server 2013 中的遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [啟用或停用 Lync Server 2013 中的遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [啟用或停用 Lync Server 2013 中的匿名使用者存取](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [指派會議原則以支援匿名使用者在 Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


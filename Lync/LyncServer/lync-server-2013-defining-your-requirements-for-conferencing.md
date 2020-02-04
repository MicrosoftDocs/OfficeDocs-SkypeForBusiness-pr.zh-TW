---
title: Lync Server 2013：定義會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中定義會議需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

決定要部署哪些會議功能時，您必須考慮您要提供給使用者的功能，以及您的網路頻寬功能。 下列問題清單可引導您完成會議規劃程式，以根據貴組織的需求來判斷您應該部署的會議功能。

  - **您想要啟用網路會議，包括檔共同作業和應用程式共用？**
    
    如果是這樣，您必須在 Microsoft Lync Server 2013、規劃工具或拓撲建立器中，為您的前端池啟用會議。 當您啟用會議時，您會同時啟用 [web 會議] 和 [A/V 會議]。
    
    應用程式共用需要和使用更多的網路頻寬，而不是檔共同作業。 Lync Server 2013 提供控制每個應用程式共用會話的節流機制。 根據預設，這會設定為每個會話的 1.5 KB/秒。
    
    如果您不想啟用應用程式共用，但想要檔共同作業，您可以啟用會議並使用會議原則來停用應用程式共用。 如需有關設定會議原則的詳細資訊，請參閱[Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。
    
    若要讓使用者能夠共用 PowerPoint 簡報，您需要設定 Office Web Apps 伺服器。 如需有關設定 Office Web Apps Server 的詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **您想要啟用 A/V 會議嗎？**
    
    如果是這樣，您必須在 Lync Server 2013、規劃工具或拓撲建立器中，為您的前端池啟用會議。 當您啟用會議時，您會同時啟用 [web 會議] 和 [A/V 會議]。
    
    A/V 會議需要並使用比 web 會議更多的網路頻寬（包括檔共同作業和應用程式共用）。 如果您不想啟用 A/V 會議，但想要啟用網路會議，您可以啟用會議並使用會議原則來停用 A/V 會議。
    
    如果您想要啟用音訊會議，但不想要啟用視訊會議，您可以啟用 A/V 會議，並使用會議原則來避免視訊會議。 或者，您也可以啟用 A/V 會議，並僅允許特定使用者開始或參與 A/V 會議。
    
    <div>
    

    > [!NOTE]  
    > 您不需要使用企業語音，您就可以使用 A/V 會議。 如果您啟用 A/V 會議，即使您在電話方案中使用 PBX，您的使用者也可以在會議中加入音訊。

    
    </div>

  - **您想要讓使用者在使用 PSTN 手機時加入會議的音訊部分嗎？**
    
    如果是，請部署並啟用電話撥入式會議。 您的組織內部和外部受邀的使用者，都可以使用 PSTN 手機加入會議的音訊部分。

  - **您想要讓 Lync Server 2013 用戶端的外部使用者加入您已啟用的會議類型嗎？**
    
    如果是這樣，您應該部署邊緣伺服器。 透過允許外部參與會議，您可以將投資最大化在 Lync Server 2013 中。 例如，擁有 Lync Server 2013 的膝上型電腦可以從在家、機場或客戶網站上的任何位置加入會議。
    
    此外，部署邊緣伺服器之後，您可以建立與其他組織的聯盟關聯，例如您的客戶或廠商，以及這些組織的使用者可以更輕鬆地與您的使用者共同作業。
    
    如需有關部署邊緣伺服器的詳細資訊，請參閱在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)，以及[在 lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。 如需啟用 Office Web Apps Server 外部 access 的詳細資料，請參閱[使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps 伺服器](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。

  - **您想要控制可加入 Lync Server 2013 會議的用戶端嗎？**
    
    如果是這樣，您應該設定會議加入頁面，以便只提供您想要支援的用戶端選項。 每當使用者按一下連結加入排程的會議時，Lync Server 2013 就會偵測到電腦上是否已安裝用戶端。 接著，它會啟動預設用戶端，並開啟 [會議加入] 頁面，其中包含備用用戶端的連結。 [會議加入] 頁面總是包含使用 Microsoft Lync Web App 的選項。 除了此選項之外，您還可以決定是否要包含出席者的連結，以及舊版的 Communicator。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 的網路會議需求](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 中的 A/V 會議需求](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的會議規劃](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 中的會議部署檢查清單](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


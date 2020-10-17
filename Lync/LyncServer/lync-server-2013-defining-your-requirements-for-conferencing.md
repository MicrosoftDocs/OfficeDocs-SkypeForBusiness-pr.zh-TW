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
ms.openlocfilehash: 9572317dc88d354f7df815be5dcb3cae4ffeba6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504370"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中定義會議需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

您在決定要部署哪些會議功能時，需要考量要提供給使用者的功能，以及網路頻寬功能。以下問題清單可在您的會議功能規劃期間，逐步引導您依據組織需求決定應該要部署的各項會議功能。

  - **您想要啟用 Web 會議功能，並納入文件共同作業及應用程式共用功能嗎？**
    
    如果是的話，您必須在 Microsoft Lync Server 2013、規劃工具或拓撲產生器中啟用前端集區的會議。 啟用會議功能時，會同時啟用 Web 會議功能及 A/V 會議功能。
    
    應用程式共用功能需要使用比文件共同作業更多的網路頻寬。 Lync Server 2013 提供節流機制來控制每個應用程式共用會話。 預設會將每一個工作階段的節流機制設為 1.5 KB/秒。
    
    若您不想要啟用應用程式共用，但需要文件共同作業功能的話，可以啟用會議功能並使用會議原則來停用應用程式共用。 如需設定會議原則的詳細資訊，請參閱 [Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。
    
    若要讓使用者能夠共用 PowerPoint 簡報，您必須設定 Office Web Apps Server。 如需設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **您想要啟用 A/V 會議功能嗎？**
    
    如果是的話，您必須在 Lync Server 2013、規劃工具或拓撲產生器中啟用前端集區的會議。 啟用會議功能時，會同時啟用 Web 會議功能及 A/V 會議功能。
    
    A/V 會議功能需要使用比 Web 會議 (包括文件共同作業和應用程式共用) 更多的網路頻寬。若您不想要啟用 A/V 會議功能，但要啟用 Web 會議功能的話，可以啟用會議功能並使用會議原則來停用 A/V 會議功能。
    
    若您想要啟用音訊會議功能，但不要視訊會議功能，可以啟用 A/V 會議功能並使用會議原則來停用視訊會議功能。或者，您可以啟用 A/V 會議功能並僅允許特定使用者啟動或參與 A/V 會議。
    
    <div>
    

    > [!NOTE]  
    > 您不需要使用企業語音，即可使用 A/V 會議。 若您啟用 A/V 會議功能，即使您的電話解決方案使用 PBX，使用者只要有音訊裝置，就可以在會議中新增音訊。

    
    </div>

  - **您想要讓使用 PSTN 電話的使用者加入會議的音訊部分嗎？**
    
    如果是的話，請部署並啟用電話撥入式會議功能。這時，來自組織內外的受邀使用者就可以透過 PSTN 電話加入會議的音訊部分。

  - **您想要讓具有 Lync Server 2013 用戶端的外部使用者加入您已啟用的會議類型嗎？**
    
    如果是的話，請部署 Edge Server。 透過允許外部參與會議，您可以在 Lync Server 2013 中達到最大的投資。 例如，擁有 Lync Server 2013 的可擕式電腦的使用者可以加入會議，不論他們身在家裡、機場或客戶網站。
    
    此外，只要部署了 Edge Server，您就可以和其他組織 (例如您的客戶或廠商) 建立同盟關係，這些組織的使用者可以輕鬆和您的使用者共同作業。
    
    如需部署 Edge server 的詳細資訊，請參閱在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 和 [部署 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。 如需啟用 Office Web Apps Server 的外部存取的詳細資訊，請參閱 [使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。

  - **您想要控制可加入 Lync Server 2013 會議的用戶端嗎？**
    
    如果是的話，請設定 [會議加入] 頁面，限制您想要支援的用戶端選項。 每當使用者按一下連結加入排程的會議時，Lync Server 2013 便會偵測是否已在電腦上安裝用戶端。 這時，它會啟動預設的用戶端並開啟 [會議加入] 頁面，其中包含其他用戶端的連結。 [會議加入] 頁面一定會包含使用 Microsoft Lync Web App 的選項。 除了此選項之外，您還可以決定是否要包含出席者和舊版 Communicator 的連結。 如需詳細資訊，請參閱 [在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的 Web 會議需求](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 中的 A/V 會議需求](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃會議](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 中會議的部署檢查清單](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


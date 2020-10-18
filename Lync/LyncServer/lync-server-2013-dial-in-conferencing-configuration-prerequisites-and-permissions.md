---
title: 電話撥入式會議設定必要條件和許可權
description: 電話撥入式會議設定必要條件和許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576169"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議設定必要條件和許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

電話撥入式會議是 Lync Server 2013 會議工作負載的選用元件。 在您使用拓撲產生器來設計拓撲，然後設定前端集區或 Standard Edition server 之前，您需要先安裝的元件，才能設定電話撥入式會議。 本主題說明您必須完成的工作，才能設定電話撥入式會議。

本節假設您已閱讀與會議工作負載和電話撥入式會議具體相關的規劃區段。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>電話撥入式會議設定必要條件

電話撥入式會議需要下列 Lync Server 2013 元件：

  - 整合通訊應用程式服務 (UCAS)  (稱為 *Application Service*) 

  - Conferencing Attendant application

  - Conferencing Announcement application

  - 電話撥入式會議設定網頁

  - 至少一部 Lync Server 2013 轉送伺服器和至少一部 PSTN 閘道

當您使用拓撲產生器來定義及發行拓撲，然後部署前端集區或 Standard Edition server 時，您就可以部署這些元件。 如果您部署的是企業語音，您應該先部署它，再設定電話撥入式會議。 如果您不是部署企業語音，您可以在部署前端集區或 Standard Edition Server 時，部署轉送伺服器和公用交換電話網路 (PSTN) 閘道。

<div>


> [!NOTE]
> 如果您要從 Office 通訊伺服器 2007 R2 升級至 Lync Server 2013，請在您計畫用於主控 Lync Server 2013 會議的每個集區中部署電話撥入式會議。 如需遷移電話撥入式會議的詳細資訊，請參閱 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013</A>。



</div>

本節假設您已完成下列作業：

  - 如果您要遷移至 Lync Server 2013，請將最新的更新套用至 Office 通訊伺服器 2007 R2 環境。

  - 使用拓撲產生器來設計及設定拓撲。 在指定會議工作負載時，您已選取 [電話撥入式會議] 選項。 如需定義拓撲的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md) 。

  - 已發行您的拓撲，並設定前端集區或 Standard Edition server。 如需發行拓撲及安裝 Lync Server 2013 的詳細資訊，請參閱部署檔中的 [部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) 。
    
    <div>
    

    > [!NOTE]
    > 當您安裝已發佈的拓撲時，電話撥入式會議設定網頁會安裝在 Web 服務中的前端伺服器或 Standard Edition server 上。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 如果您在部署 Lync Server 2013 之後，在拓撲產生器中變更檔存放區的路徑，您必須重新開機會議助理和會議宣告應用程式，才能使用新的路徑。

    
    </div>

  - 已部署的 Enterprise Voice。 如果您不是部署企業語音，您可以組合 Enterprise Edition 前端伺服器或 Standard Edition server 上的轉送伺服器，或是部署了獨立轉送伺服器，並已部署 PSTN 閘道。 如需部署企業語音的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中部署 Enterprise Voice](lync-server-2013-deploying-enterprise-voice.md) 。 如需安裝獨立轉送伺服器和 PSTN 閘道的詳細資訊，請參閱部署檔中的部署中繼 [伺服器及定義 Lync Server 2013 中的對等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) 專案。

下列流程圖顯示您必須執行的步驟，才能設定電話撥入式會議，以及設定電話撥入式會議所執行的步驟。

**部署電話撥入式會議**

![電話撥入式會議部署流程圖](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "電話撥入式會議部署流程圖")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>電話撥入式會議許可權

若要設定電話撥入式會議，您需要使用下列系統管理工具：

  - Lync Server 2013 控制台

  - Lync Server 管理命令介面

您可以使用這些系統管理工具來設定電話撥入式會議設定，以及電話撥入式會議所需的撥號對應表、原則及其他設定。

設定電話撥入式會議需要下列任何系統管理角色，視任務而定：

  - **CsVoiceAdministrator**    此系統管理員角色可以建立、設定及管理語音相關的設定和原則。

  - **CsUserAdministrator**    此系統管理員角色可以啟用和停用 Lync Server 的使用者，並將現有的原則（例如會議原則和 PIN 碼原則）指派給使用者。

  - **CsAdministrator**    此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署企業語音](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


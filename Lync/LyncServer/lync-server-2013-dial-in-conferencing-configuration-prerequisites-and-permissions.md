---
title: 電話撥入式會議組態先決條件和權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議組態先決條件和權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

電話撥入式會議是 Lync Server 2013 會議工作負載的選用元件。 在您使用 [拓撲建立器] 設計拓撲，然後設定您的 [前端] 池或標準版伺服器之後，您必須先安裝所需的元件，才能設定電話撥入式會議。 本主題說明您必須先完成的工作，才能設定電話撥入式會議。

本節假設您已閱讀與會議工作負載和電話撥入式會議相關的規劃區段。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>電話撥入式會議設定的先決條件

電話撥入式會議需要下列 Lync Server 2013 元件：

  - 整合通訊應用程式服務（UCAS）（稱為*應用程式服務*）

  - 會議助理應用程式

  - 會議公告應用程式

  - 電話撥入式會議設定網頁

  - 至少有一個 Lync Server 2013 轉送伺服器和至少一個 PSTN 閘道

當您使用 [拓撲建立器] 定義併發布拓撲，然後部署前端池或標準版伺服器時，就會部署這些元件。 如果您要部署企業語音，您應該先部署它，然後再設定電話撥入式會議。 如果您不是部署企業語音，您可以在部署前端池或標準版伺服器時，部署中繼伺服器和公用交換電話網絡（PSTN）閘道。

<div>


> [!NOTE]
> 如果您是從 Office 通訊伺服器 2007 R2 升級到 Lync Server 2013，請在您打算用來主持 Lync Server 2013 會議的每個池中部署電話撥入式會議。 如需有關移植電話撥入式會議的詳細資訊，請參閱<A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">從 Office 通訊伺服器 2007 R2 遷移到 Lync Server 2013</A>。



</div>

本節假設您已完成下列作業：

  - 將最新的更新套用至您的 Office 通訊伺服器 2007 R2 環境（如果您要遷移至 Lync Server 2013）。

  - 使用 [拓撲建立器] 來設計及設定您的拓撲。 在指定會議工作量時，您已選取 [電話撥入式會議] 選項。 如需定義拓朴的詳細資料，請參閱部署檔中的[Lync Server 2013 中的定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

  - 已發佈您的拓撲，並設定前端池或標準版伺服器。 如需發佈拓撲及安裝 Lync Server 2013 的詳細資料，請參閱部署檔中的 [[部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) ]。
    
    <div>
    

    > [!NOTE]
    > 當您安裝已發佈的拓撲時，系統會在前端伺服器或標準版伺服器上安裝 [電話撥入式會議設定] 網頁，成為 Web 服務的一部分。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 如果您在部署 Lync Server 2013 之後，在 [拓撲建立器] 中變更了檔案存放區的路徑，您必須重新開機會議助理與會議發佈應用程式，才能使用新的路徑。

    
    </div>

  - 已部署企業語音。 如果您不是部署企業語音，您可以在企業版前端伺服器或標準版伺服器上 collocated 中繼伺服器，或部署獨立的中繼伺服器，且已部署 PSTN 閘道。 如需部署企業語音的詳細資料，請參閱部署檔中的[Lync Server 2013 中的部署企業語音](lync-server-2013-deploying-enterprise-voice.md)。 如需安裝獨立的中繼伺服器和 PSTN 閘道的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中部署轉送伺服器和定義對等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)。

下列流程圖顯示您必須執行的步驟，才能設定電話撥入式會議，以及設定電話撥入式會議所需執行的步驟。

**部署電話撥入式會議**

![電話撥入式會議部署流程圖][(images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "電話撥入式會議] 部署流程圖")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>電話撥入式會議許可權

若要設定電話撥入式會議，您需要使用下列管理工具：

  - Lync Server 2013 [控制台]

  - Lync Server 管理命令介面

您可以使用這些管理工具來設定電話撥入式會議設定，以及撥號方案、原則及其他電話撥入式會議所需的設定。

設定電話撥入式會議需要下列任何一個管理角色，視任務而定：

  - **CsVoiceAdministrator**   此系統管理員角色可以建立、設定及管理語音相關設定與原則。

  - **CsUserAdministrator**   此系統管理員角色可以啟用和停用 Lync Server 的使用者，並將現有的原則（例如會議原則及 PIN 原則）指派給使用者。

  - **CsAdministrator**   此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署企業版語音](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


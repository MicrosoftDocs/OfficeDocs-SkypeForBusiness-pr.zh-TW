---
title: Lync Server 2013：部署常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中部署常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-31_

Lync server 2013，持續聊天伺服器是 Lync Server 2013 基礎結構的一部分。

部署持久聊天伺服器時，您必須：

  - 使用拓撲建立器來定義或匯入，並隨後發佈您要部署的拓撲和元件。

  - 準備部署持久聊天伺服器元件的環境。

  - 針對您的部署安裝及設定持續聊天伺服器元件。

在 Lync Server 2013 企業版中，您可以使用永久性聊天伺服器作為獨立的文件庫（而不是與企業版前端伺服器 collocated）。 持續聊天伺服器需要企業版池中的 SQL Server 後端伺服器，才能儲存聊天室內容和其他相關中繼資料。 我們建議您將**PersistentChatStore**安裝在專用的 Sql Server 後端伺服器上，不過 Collocating 的 Lync Server 2013 後端伺服器和**PersistentChatStore**都支援相同的 sql server 實例。

持久聊天伺服器也可以使用 Lync Server 2013 標準版來部署。 在這種情況下， **PersistentChatService**前端伺服器是在標準版電腦上 collocated，而**PersistentChatStore**後端伺服器可以部署在本機 SQL Server Express 實例上。

如需支援的 colocation 設定的詳細資訊，請參閱[Lync server 2013 中支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md)。

<div>


> [!IMPORTANT]  
> 我們不支援持續聊天伺服器&nbsp;標準版的高可用性。 效能和比例會受到限制。 此外，我們只支援新的持續聊天&nbsp;伺服器標準版伺服器。 我們不支援將 Lync Server 2010、群組聊天伺服器升級為 Lync Server 2013&nbsp;持續聊天伺服器&nbsp;標準版。



</div>

如果您的組織需要合規性支援，您可以在永久聊天伺服器前端伺服器上安裝持續式聊天伺服器合規性服務。 需要一個單獨的資料庫來實現合規性。

每個拓撲至少都需要裝有 Lync Server 2013 的伺服器，以及已安裝 SQL Server database 軟體的伺服器。

使用拓撲建立器，將持續聊天伺服器新增到您的 Lync Server 2013 部署。 您可以選擇使用 [拓撲建立器] 新增一或多個持續聊天伺服器池。 遵循相同的部署指示來部署多個持續聊天伺服器池，就像為任何一個池所做的一樣。 如需詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。

如需有關可用拓撲的詳細資料，以及安裝持續聊天伺服器的技術和軟體需求，請參閱規劃[2013](lync-server-2013-how-persistent-chat-server-works.md)檔中的 [在 lync server [2013 中規劃持久聊天](lync-server-2013-planning-for-persistent-chat-server.md)伺服器]、[安裝] 檔、部署檔或操作檔，以及[支援的 lync server 2013 硬體](lync-server-2013-supported-hardware.md)（在可支援檔中）。

如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。

單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。 您可以使用最多4個作用中的 [永久聊天伺服器] 池，同時支援全部80000並行使用者。

虛擬伺服器也支援持續式聊天伺服器。 如果虛擬伺服器符合物理伺服器的規格，就能支援最多20000個併發使用者。

<div>


> [!IMPORTANT]  
> 持續聊天伺服器必須安裝在 NTFS 檔案系統上，以協助強制執行檔案系統安全性。 FAT32 不是持久聊天伺服器所支援的檔案系統。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中，持久聊天伺服器的運作方式](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 中的常設聊天室伺服器的部署檢查清單](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 中持續聊天伺服器的技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中設定常設聊天室伺服器的系統與基礎結構](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中將常設聊天室伺服器新增至您的部署](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [在 Lync Server 2013 中安裝常設聊天室伺服器](lync-server-2013-installing-persistent-chat-server.md)

  - [在 Lync Server 2013 中新增常設聊天室管理員](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [在 Lync Server 2013 中設定常設聊天室伺服器](lync-server-2013-configuring-persistent-chat-server.md)

  - [使用 Windows PowerShell Cmdlet 設定常設聊天室伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 疑難排解常設聊天室伺服器設定](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中針對高可用性和災害復原設定常設聊天室伺服器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2013 中的容錯移轉和容錯回復常設聊天室伺服器](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


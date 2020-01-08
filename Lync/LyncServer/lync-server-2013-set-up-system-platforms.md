---
title: Lync Server 2013：設定系統平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>在 Lync Server 2013 中設定系統平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

開始部署持久聊天伺服器之前，您必須在符合伺服器上系統需求的硬體上安裝所需的作業系統：

如需執行 Lync Server 2013、資料庫伺服器和檔案伺服器之伺服器支援的硬體相關詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。 如需支援的作業系統和資料庫軟體的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。 如需有關 Windows 更新需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)。

永久聊天伺服器前端伺服器（ **PersistentChatService**）可在 Lync Server 2013 企業版文件庫中的一或多台獨立電腦上部署。 在 Lync Server Enterprise Edition 前端伺服器上無法 collocated。 引導程式可以部署持久聊天伺服器，就像其他 Lync 伺服器角色一樣。 [檔案**上傳]/[下載**] 與 [**聊天室管理**] 的持續聊天 Web 服務是在 Lync Server 2013 前端伺服器上部署的網頁元件。

單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。 您可以使用最多4個作用中的持續聊天伺服器池，以支援總共80000個併發使用者。 持續聊天后端伺服器（ **PersistentChatStore**）會儲存聊天室和類別。 我們建議您在企業版文件庫的專用 SQL Server 後端伺服器上安裝**PersistentChatStore** ;雖然我們支援 collocating Lync Server 2013 後端伺服器和**PersistentChatStore**在相同的 SQL Server 實例上。

如果您的組織需要合規性支援，您可以使用 [拓撲建立器] 進行安裝。 永久聊天伺服器合規性服務會安裝在與永久聊天伺服器前端伺服器相同的電腦上。 需要一個單獨的資料庫來實現合規性。 如需持續聊天伺服器的規範需求的詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。

每個拓撲至少都需要裝有 Lync Server 2013 的伺服器，以及已安裝 SQL Server database 軟體的伺服器。 拓撲建造器支援多個持續聊天伺服器池。 遵循相同的部署指示來部署多個持續聊天伺服器池，就像您在部署檔中[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)的任何池一樣。

您也可以使用 Lync Server 2013 標準版來部署持久聊天伺服器。 在這種情況下， **PersistentChatService**前端伺服器是在標準版 server 上 collocated，您可以在本機 SQL Server Express 實例上部署**PersistentChatStore**後端伺服器。

<div>


> [!IMPORTANT]  
> 我們不支援持續聊天伺服器&nbsp;標準版來提供高可用性。 效能和比例會受到限制。 此外，我們只支援新的持續聊天&nbsp;伺服器標準版伺服器部署。 我們不支援 Lync Server 2010 的升級，將 [群組聊天伺服器] 升級為 Lync Server&nbsp;2013 持續聊天&nbsp;伺服器標準版。



</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013 的受支援硬體](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)  
[在 Lync Server 2013 中規劃常設聊天室伺服器](lync-server-2013-planning-for-persistent-chat-server.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


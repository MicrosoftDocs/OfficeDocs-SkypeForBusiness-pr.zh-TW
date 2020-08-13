---
title: Lync Server 2013：設定系統平臺
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59aafcda7cbe94401cdbd77479eecf38e3e9e351
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>在 Lync Server 2013 中設定系統平臺

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

開始部署 Persistent Chat Server 之前，您必須在符合伺服器上系統需求的硬體上安裝必要的作業系統：

如需執行 Lync Server 2013、資料庫伺服器及檔案伺服器之伺服器支援硬體的詳細資訊，請參閱支援檔中的[支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md)。 如需支援的作業系統和資料庫軟體的詳細資訊，請參閱支援檔中的[伺服器軟體和基礎結構支援（Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) ）。 如需 Windows 更新需求的詳細資訊，請參閱支援檔中的[其他伺服器支援和 Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md)中的需求。

Persistent Chat Server 前端伺服器（ **PersistentChatService**）可以部署在 Lync Server 2013 Enterprise Edition 集區中的一或多個獨立電腦上。 它們無法在 Lync Server Enterprise Edition 前端伺服器上組合。 與其他 Lync Server 角色一樣，引導程式可以部署 Persistent Chat Server。 在 Lync Server 2013 前端伺服器上部署的「**檔上傳**」和「**持久聊天 web 服務」的聊天室管理**的 persistent chat web 服務是部署在 Lync Server 前端伺服器上的網頁元件。

單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。 您可以有最多4個作用中前端的持久聊天伺服器集區，支援總80000並行使用者。 Persistent Chat 後端伺服器（ **PersistentChatStore**）會儲存聊天室和類別。 建議您在 Enterprise Edition 集區的專用 SQL Server 後端伺服器上安裝**PersistentChatStore** ;雖然我們支援在相同的 SQL Server 實例上組合 Lync Server 2013 後端伺服器和**PersistentChatStore** 。

如果您的組織需要規範支援，您可以使用拓撲產生器進行安裝。 Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。 合規性需要個別的資料庫。 如需有關 Persistent Chat Server 之規範需求的詳細資訊，請參閱規劃檔中的在[Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。

每個拓撲至少需要安裝 Lync Server 2013 的伺服器，以及已安裝 SQL Server 資料庫軟體的伺服器。 拓撲產生器支援多個 Persistent Chat Server 集區。 依照部署檔中部署[Lync server 2013](lync-server-2013-deploying-lync-server.md)的任何集區的方式，遵循相同的部署指示來部署多個持久聊天伺服器集區。

您也可以使用 Lync Server 2013 Standard Edition 部署 Persistent Chat Server。 在此情況下， **PersistentChatService**前端伺服器在 Standard Edition Server 上是組合的，您可以在本機 SQL Server Express 實例上部署**PersistentChatStore**後端伺服器。

<div>


> [!IMPORTANT]  
> 我們不支援 Persistent Chat Server &nbsp; Standard Edition 高可用性。 效能及規模將會受到限制。 此外，我們僅支援新的持久聊天伺服器 &nbsp; Standard Edition server 部署。 我們不支援將 Lync Server 2010，Group Chat Server 升級成 Lync Server 2013 &nbsp; Persistent Chat server &nbsp; Standard Edition。



</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013 的支援硬體](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)  
[在 Lync Server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


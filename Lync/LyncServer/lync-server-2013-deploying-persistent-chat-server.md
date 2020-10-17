---
title: Lync Server 2013：部署 Persistent Chat Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76f3bb2a3ccc182f16e2e1416bdec00aefe3e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506090"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Persistent Chat Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-31_

Lync Server 2013，Persistent Chat Server 是 Lync Server 2013 基礎結構的一部分。

部署 Persistent Chat Server 需要您：

  - 使用拓撲產生器來定義或匯入，然後發佈您要部署的拓撲和元件。

  - 準備部署持久聊天伺服器元件的環境。

  - 為您的部署安裝及設定 Persistent Chat Server 元件。

Persistent Chat Server 可搭配 Lync Server 2013 Enterprise Edition 做為個別集區 (不會與 Enterprise Edition 前端伺服器) 進行組合。 Persistent Chat Server 要求企業版集區中的 SQL Server 後端伺服器，以儲存聊天室內容及其他相關的中繼資料。 建議您將 **PersistentChatStore** 安裝在專用的 Sql Server 後端伺服器上，不過在相同的 sql server 實例上，組合 Lync Server 2013 後端伺服器和 **PersistentChatStore** 皆受支援。

Persistent Chat Server 也可以與 Lync Server 2013 Standard Edition 一起部署。 在此情況下，Standard Edition 電腦上的 **PersistentChatService** 前端伺服器是組合， **PersistentChatStore** 後端伺服器可部署在本機 SQL Server Express 實例上。

如需支援的 colocation 設定的詳細資訊，請參閱 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md)。

<div>


> [!IMPORTANT]  
> 我們不支援 Persistent Chat Server Standard Edition 的高可用性 &nbsp; 。 效能及規模將會受到限制。 此外，我們僅支援新的 Persistent Chat Server &nbsp; Standard Edition server。 我們不支援將 Lync Server 2010，Group Chat Server 升級成 Lync Server 2013 &nbsp; Persistent Chat server &nbsp; Standard Edition。



</div>

如果您的組織需要規範支援，您可以在 Persistent Chat Server 前端伺服器上安裝 Persistent Chat Server 合規性服務。 合規性需要個別的資料庫。

每個拓撲至少需要安裝 Lync Server 2013 的伺服器，以及已安裝 SQL Server 資料庫軟體的伺服器。

使用拓撲產生器，將 Persistent Chat Server 新增至您的 Lync Server 2013 部署。 您可以選擇使用拓撲產生器來新增一或多個 Persistent Chat Server 集區。 遵循部署多個 Persistent Chat Server 集區的相同部署指示。 如需詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

如需有關安裝 Persistent Chat Server 的可用拓撲及技術和軟體需求的詳細資訊，請參閱規劃檔、部署檔或作業檔中的「在 lync server [2013](lync-server-2013-how-persistent-chat-server-works.md)中[規劃 Persistent chat 2013 server](lync-server-2013-planning-for-persistent-chat-server.md) 」，以及支援檔中的[lync server 2013 的支援硬體](lync-server-2013-supported-hardware.md)。

如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。 您最多可以有最多4個作用中前端伺服器的持久聊天伺服器集區，以支援所有80000並行使用者。

虛擬伺服器也支援 Persistent Chat Server。 虛擬伺服器若符合實體伺服器的規格，最多可支援20000並行使用者。

<div>


> [!IMPORTANT]  
> 必須在 NTFS 檔案系統上安裝 Persistent Chat Server，以協助強制執行檔案系統安全性。 FAT32 不是持久聊天伺服器支援的檔案系統。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中，Persistent Chat Server 的運作方式](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 中 Persistent Chat Server 的部署檢查清單](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 中 Persistent Chat Server 的技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中設定 Persistent Chat Server 的系統和基礎結構](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中將 Persistent Chat Server 新增至您的部署](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [在 Lync Server 2013 中安裝 Persistent Chat Server](lync-server-2013-installing-persistent-chat-server.md)

  - [在 Lync Server 2013 中新增 Persistent Chat 系統管理員](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [在 Lync Server 2013 中設定 Persistent Chat Server](lync-server-2013-configuring-persistent-chat-server.md)

  - [使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [使用 Lync Server 2013 中的 Windows PowerShell Cmdlet 來疑難排解 Persistent Chat Server 設定](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中設定持久聊天伺服器以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [在 Lync Server 2013 中容錯移轉和失敗回復持久聊天伺服器](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


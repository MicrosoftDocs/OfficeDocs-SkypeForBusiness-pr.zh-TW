---
title: 配置 Lync Server 以搭配 System Center Operations Manager 使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>設定 Lync Server 2013 以搭配 System Center Operations Manager 使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

若要設定您的 Microsoft Lync Server 2013 基礎結構以搭配 System Center Operations Manager 使用，您必須執行下列三項操作：

  - 找出並設定您的主要 System Center Operations Manager 管理伺服器。 配置管理伺服器包括安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 設定後端資料庫。 您需要使用的實際 SQL Server 版本，取決於您所使用的 System Center 作業管理員版本。 如需詳細資訊，請參閱[在 Lync server 2013 中設定主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)。

  - 找出並設定您想要監視的 Lync 伺服器電腦。 若要使用 System Center Operations Manager 監視 Lync Server 電腦，您必須安裝 System Center Operations Manager 代理檔案，並將每個伺服器設定為充當 proxy。

  - 找出並設定您想要充當 Lync Server*觀察程式節點*的電腦。 [觀察程式] 節點是定期執行 Lync Server 綜合交易的電腦，這些 Cmdlet 是確認重要 Lync 伺服器元件（例如登入系統或 exchange 立即訊息功能）的 Windows PowerShell Cmdlet。如預期的方式運作。

本節中的主題包含執行這些任務的指示。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)

  - [安裝 Lync Server 2013 管理套件](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [設定將在 Lync Server 2013 中監視的 Lync Server 電腦](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [在 Lync Server 2013 中安裝及設定觀察程式節點](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


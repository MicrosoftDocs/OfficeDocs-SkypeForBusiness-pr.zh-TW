---
title: 設定 Lync Server 以與 System Center Operations Manager 搭配使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150b240fe0c2be769e407cacecd8440bd4596ae5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506230"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>設定 Lync Server 2013 以與 System Center Operations Manager 搭配使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

為了設定您的 Microsoft Lync Server 2013 基礎結構，與 System Center Operations Manager 搭配使用，您必須執行下列三項動作：

  - 識別及設定您的主要 System Center Operations Manager 管理伺服器。 設定管理伺服器包括安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 設定後端資料庫。 您需要使用的實際 SQL Server 版本，取決於您所使用的 System Center Operations Manager 版本。 如需詳細資訊，請參閱 [在 Lync server 2013 中設定主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)。

  - 識別及設定您要監視的 Lync Server 電腦。 若要使用 System Center Operations Manager 監視 Lync Server 電腦，您必須安裝 System Center Operations Manager 代理程式檔案，並設定每一部伺服器充當 proxy。

  - 識別及設定您要充當 Lync Server *觀察器節點*的電腦。 監看員節點是定期執行 Lync Server 綜合交易的電腦，其為 Windows PowerShell Cmdlet，用來驗證重要的 Lync Server 元件（例如，登入系統或 exchange 立即訊息功能可如預期的方式運作）。

本節中的主題包含執行下列每一項工作的指示。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)

  - [安裝 Lync Server 2013 管理套件](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [設定將在 Lync Server 2013 中監控的 Lync Server 電腦](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [在 Lync Server 2013 中安裝及設定觀察程式節點](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


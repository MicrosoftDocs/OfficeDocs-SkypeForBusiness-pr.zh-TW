---
title: 設定 Lync Server 以搭配 System Center Operations Manager
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
ms.openlocfilehash: ff72248e691d3e5358fda79a98d318cfc3a382eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>設定 Lync Server 2013 來使用 System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

若要設定您的 Microsoft Lync Server 2013 基礎結構，以搭配 System Center Operations Manager 中，您必須執行下列三個動作：

  - 找出並將您主要的 System Center Operations Manager 管理伺服器設定。 設定管理伺服器包括安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及設定使用 SQL Server 後端資料庫。 您必須使用 SQL Server 的實際版本取決於您使用 System Center Operations Manager 的版本。 如需詳細資訊，請參閱[設定 Lync Server 2013 中的主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)。

  - 找出並設定您想要監視的 Lync Server 電腦。 若要使用 System Center Operations Manager 監視 Lync Server 的電腦中，您必須安裝 System Center Operations Manager 代理程式檔案，並設定每一部要作為 proxy。

  - 找出並設定您想要做為 Lync Server*監看員節點*的電腦。 監看員節點會定期執行 Lync Server 綜合交易，也就是確認重要的 Lync Server 元件，例如能夠登入系統或交換立即訊息的能力的 Windows PowerShell cmdlet 的電腦如預期運作。

本節中的主題包含執行每項工作的指示。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定的主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)

  - [安裝 Lync Server 2013 管理組件](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [在 Lync Server 2013 中設定要監控的 Lync Server 電腦](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [安裝和設定 Lync Server 2013 中的監看員節點](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：支援的伺服器遷移路徑和共存案例
description: Lync Server 2013：支援的伺服器遷移路徑和共存案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560229"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013 中支援的伺服器遷移路徑和共存案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

Lync Server 2013 支援從下列其中一項進行遷移：

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

同時執行這兩個舊版的環境無法進行移轉。 不支援從早期版本（如 Microsoft Office 通訊伺服器2007或 Live 通訊伺服器2005）進行遷移。 如果您先前的部署包含群組聊天，您必須另行遷移。

<div>

## <a name="migration-methods"></a>移轉方法

支援所有 Lync Server 拓撲和伺服器角色的遷移。 您可以從某一種拓撲移轉至不同的拓撲，包括從 Standard Edition Server 移轉至 Enterprise Edition Server 在內。

Lync Server 2013 僅支援下列遷移方法：

  - <span></span>  
    **並存移轉。** 在並列遷移中，Lync Server 2013 是隨現有的 Microsoft Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署一起部署，然後將作業轉移至新的伺服器，並將使用者移至 Lync Server 2013。 此方法在移轉期間需要額外的伺服器平台 (包括軟硬體)，且新設定中的系統名稱和集區名稱會不相同。 若有需要復原為先前的版本，您可以將作業切換回先前的伺服器。

不支援跨 Active Directory 網域服務目錄樹進行遷移。

建議您採用分段執行的移轉路徑。如需從舊版進行移轉的詳細資訊 (包括將元件部署適當分段的方式)，請參閱下列移轉文件中的主題：

  - [從 Lync Server 2010 遷移至 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>並存案例

Lync Server 2013 可以與 Lync Server 2010 部署或 Office 通訊伺服器 2007 R2 部署的元件共存。 同時部署 Lync Server 2013 和 Lync Server 2010 和 Office 通訊伺服器 2007 R2 (所有三個版本) 的同時部署都不受支援。

在分段遷移期間，舊的 Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署會暫時使用新的 Lync Server 2013 部署 coexists，混合式版本路由的支援會受到限制。 如需詳細資訊，請參閱移轉文件。

您必須針對 Lync Server 2013 資料庫實例，使用執行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 的個別及不同電腦。 您無法使用相同的 SQL Server 實例作為 lync server 2010 或 Office 通訊伺服器 2007 R2 前端集區所使用的 Lync Server 2013 前端集區。 如果您在拓撲產生器中為已部署 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的部署定義及設定 Lync Server 2013，拓撲產生器將不會允許您定義已在拓撲中使用的 Lync Server 2013 實例。

拓撲產生器會顯示下列訊息，以通知您發生此問題：「伺服器的 SQL server \[ FQDN \] 已包含主控角色 ' 使用者存放區」的 sql 實例。

<div>


> [!NOTE]  
> 如果您想要部署 Lync Server 2013 部署中新的伺服器角色，您應該先升級現有的部署，如遷移檔和部署檔中所述，然後根據規劃檔和部署檔中所述，部署新的伺服器角色。 如果您要遷移舊版的群組聊天，請在最後開始，在完成從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 遷移所有其他元件的程式之後，再進行遷移。



</div>

如需有關 Lync Server 2010 或 Office 通訊伺服器 2007 R2 和 Lync Server 2013 元件共存及遷移的特定共存需求和其他詳細資料，請參閱遷移檔中的 [從 Lync server 2010 遷移至 lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 及 [從 Office 通訊伺服器 2007 R2 遷移至 lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 。 如需用戶端混合版本支援的詳細資訊，請參閱 [Lync Server 2013 中的先前部署支援的用戶端](lync-server-2013-supported-clients-from-previous-deployments.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


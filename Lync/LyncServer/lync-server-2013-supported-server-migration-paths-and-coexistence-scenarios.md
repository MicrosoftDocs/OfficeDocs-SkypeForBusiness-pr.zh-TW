---
title: Lync Server 2013：支援的伺服器轉移路徑和並存案例
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
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013 中支援的伺服器轉移路徑和並存案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

Lync Server 2013 支援從下列其中一項進行遷移：

  - Microsoft Lync Server 2010

  - Microsoft Office 通訊伺服器 2007 R2

不支援從執行這兩個舊版版本的環境進行遷移。 不支援從較舊的版本（例如 Microsoft Office 通訊伺服器2007或即時通訊伺服器2005）遷移。 如果您先前的部署包含群組聊天，您必須另行遷移。

<div>

## <a name="migration-methods"></a>遷移方法

支援遷移所有 Lync Server 拓撲和伺服器角色。 您可以從一個拓撲遷移至不同拓撲，包括從標準版伺服器到企業版伺服器。

Lync Server 2013 只支援下列遷移方法：

  - <span></span>  
    **並行遷移。** 在並列式遷移中，Lync Server 2013 是與現有的 Microsoft Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署一起部署，然後您將作業轉移到新的伺服器，並將使用者移至 Lync Server 2013。 這個方法需要其他伺服器平臺，包括硬體和軟體，在遷移期間，系統名稱和池名稱在新的配置中是不一樣的。 如果需要回滾到前一個版本，您可以將作業移回先前的伺服器。

不支援跨 Active Directory 網域服務林的遷移。

建議的遷移路徑是分階段的方法。 如需從舊版進行遷移的詳細資料，包括元件部署的適當分段，請參閱遷移檔中的下列主題：

  - [從 Lync Server 2010 移轉到 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [從 Office Communications Server 2007 R2 移轉至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>共存案例

Lync Server 2013 可與 Lync Server 2010 部署或 Office 通訊伺服器 2007 R2 部署的元件共存。 同時使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 （這三個版本的並行部署）不支援同時部署 Lync Server 2013。

在第一次使用新的 Lync server 2013 部署 coexists 暫時的 Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署期間，混合版本路由的支援會受到限制。 如需詳細資訊，請參閱遷移檔。

您必須針對 Lync Server 2013 資料庫實例，使用個別且獨立的電腦執行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。 您無法針對 Lync Server 2010 或 Office 通訊伺服器 2007 R2 前端池使用的 Lync Server 2013 前端池使用相同的 SQL Server 實例。 如果您在拓撲建立器中針對已部署 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的部署定義並設定 Lync Server 2013，拓撲建立器將不允許您定義已在其中使用的 Lync Server 2013 實例拓撲。

[拓撲建立器] 會顯示下列訊息，告知您有這個問題：「SQL \[server FQDN\]已包含託管角色 ' 使用者存儲」的 sql 實例。」

<div>


> [!NOTE]  
> 如果您想要部署 Lync Server 2013 部署中新的伺服器角色，您應該先升級現有的部署，如以下所述：遷移檔和部署檔中所述，然後部署新的伺服器角色，如中所述。規劃檔與部署檔。 如果您要遷移舊版群組聊天，請在完成將所有其他元件從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 遷移之後，再將它遷移到最後一個版本。



</div>

如需特定的共存需求，以及有關 Lync Server 2010 或 Office 通訊伺服器 2007 R2 和 Lync Server 2013 元件的共存與遷移的其他詳細資料，請參閱[從 Lync server 2010 遷移至 Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) ，以及[從 Office 通訊伺服器 2007 R2 遷移到 lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) （在遷移檔中）。 如需用戶端混合版本支援的詳細資料，請參閱[Lync Server 2013 中先前部署的支援的用戶端](lync-server-2013-supported-clients-from-previous-deployments.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：執行 Lync Server 2013 之伺服器的系統需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301cd234e2218fc806423a9ffe9beb49994402f2
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104492"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>執行 Lync Server 2013 之伺服器的系統需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

<div>


> [!NOTE]  
> 如需硬體需求的詳細資訊，請參閱<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>。



</div>

標準版與企業版伺服器共用相同的軟體需求。

執行 Lync Server 2013 的伺服器，企業版是適用于大型組織的主要組織部署。 企業版伺服器的設計目的是針對每個池中的大約80000穴使用者進行縮放。 運行 Lync Server 2013 的伺服器，標準版是針對較小的組織和來自主要組織部署的遠端位置而設計。 一對標準版版本伺服器最多可支援5000個使用者。 如需有關標準版伺服器與企業版伺服器之間差異的詳細資訊，請參閱[Lync Server 2013 的部署概述](lync-server-2013-deployment-overview.md)。

<div>

## <a name="operating-system-installation"></a>作業系統安裝

<div>


> [!IMPORTANT]  
> Lync Server 2013 只能在64位版本中使用，這需要64位的硬體和64位版本的 Windows Server 作業系統。 此版本不提供32位版本的 Lync Server 2013。



</div>

標準版與企業版 server 可以使用下列任何一項：

  - Windows Server 2008 R2 SP1 或最新的 service pack

  - Windows Server 2012

  - Windows Server 2012 R2

在標準版 Server 或 Enterprise Edition 前端伺服器上安裝作業系統軟體。 套用所有更新，讓作業系統的最新更新與必要更新層級與貴組織的標準一致。 如需有關操作需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

> [!NOTE] Lync Server 2013 不支援就地升級作業系統。  您必須部署個別的 [池]，並將使用者遷移到具有不同作業系統的新池。

<div>


> [!NOTE]  
> 若要讓 Lync Server 2013 在 Windows Server 2012 R2 上運作，您可能需要在 Windows Server 中變更登錄機碼的值。 您可能需要此變更，才能正常運作證書，以及讓用戶端向 Survivable 分支裝置註冊。 如需詳細資訊， <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>請參閱。



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 的其他軟體

除了作業系統所需的更新之外，Lync Server 2013 還需要作業系統角色、功能和軟體才能運作。 如需在發佈拓撲及安裝 Lync Server 2013 之前必須安裝的其他軟體的詳細資訊，請參閱規劃檔中[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>所有伺服器角色所需的其他軟體

在所有伺服器角色上，您也必須確認已安裝 Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5。

此外，任何您要執行 Lync Server 系統管理工具的電腦都必須具備 Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5。

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3。0

Lync Server 2013 需要您在將參與 Lync Server 拓撲的每一台電腦上安裝 Windows PowerShell 3.0。 如需安裝 Windows PowerShell 3.0 的詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

<div>


> [!NOTE]  
> 在 Windows Server&nbsp;2008&nbsp;R2 （含 SP1）上，在安裝 Microsoft .net Framework 4.5 之前，windows PowerShell 命令列介面3.0 無法安裝。



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4。5

當您在 Windows Server 2012 或 Windows Server 2012 R2 上執行 Lync Server 2013 的伺服器上安裝 Microsoft .NET Framework 4.5 時，您必須執行一個額外步驟。 安裝 .NET Framework 4.5 之後，請使用伺服器管理員來安裝 HTTP 啟用。

**在 Windows Server 2012 或 Windows Server 2012 R2 上安裝 .NET 4.5 HTTP 啟用**

1.  從 [**開始**] 功能表，按一下 [**程式**]，然後按一下 [**管理工具**]，再按一下 [**伺服器管理員**]。

2.  在 [伺服器管理員] 的 [**功能摘要**] 底下，選擇 [**新增功能**]。

3.  展開 [ **.Net Framework 4.5**]。

4.  選取 [ **WCF 啟用**] （如果尚未選取的話）。 然後選取 [ **HTTP 啟用**]。

5.  按一下 **[下一步**]，然後依照提示完成安裝。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


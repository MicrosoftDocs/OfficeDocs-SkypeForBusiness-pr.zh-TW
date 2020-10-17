---
title: Lync Server 2013：執行 Lync Server 2013 之伺服器的系統需求
description: Lync Server 2013：執行 Lync Server 2013 之伺服器的系統需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562649"
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
> 如需硬體需求的詳細資訊，請參閱 <A href="lync-server-2013-server-hardware-platforms.md">伺服器硬體平臺的 Lync Server 2013</A>。



</div>

Standard Edition 和 Enterprise Edition 伺服器共用相同的軟體需求。

執行 Lync Server 2013 Enterprise Edition 的伺服器專為大型組織做為主要組織部署。 Enterprise Edition Server 依設計最多可讓每個集區容納約 80,000 個使用者。 執行 Lync Server 2013 的伺服器，Standard Edition 是針對小型組織和主要組織部署的遠端位置而設計。 一對的 Standard Edition 伺服器最多可支援5000使用者。 如需有關 Standard Edition server 和 Enterprise Edition server 之間差異的詳細資訊，請參閱 [Lync Server 2013 的部署概況](lync-server-2013-deployment-overview.md)。

<div>

## <a name="operating-system-installation"></a>作業系統安裝

<div>


> [!IMPORTANT]
> Lync Server 2013 只適用于64位的版本，需要有64位的硬體和64版本的 Windows Server 作業系統。 此版本不提供 Lync Server 2013 的32位版本。



</div>

Standard Edition 和 Enterprise Edition server 可以使用下列任何一項：

  - Windows Server 2008 R2 SP1 或最新的 service pack

  - Windows Server 2012

  - Windows Server 2012 R2

在 Standard Edition Server 或 Enterprise Edition 前端伺服器上安裝作業系統軟體。 套用所有更新，讓作業系統具有與組織的標準相符的最新更新和必要更新層級。 如需有關運作需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

> [!NOTE] 
> Lync Server 2013 不支援就地升級作業系統。  您必須部署個別的集區，並將使用者遷移至具有不同作業系統的新集區。

<div>


> [!NOTE]
> 若要讓 Lync Server 2013 在 Windows Server 2012 R2 上運作，您可能需要在 Windows Server 中變更登錄機碼的值。 若要讓憑證正確運作，且要讓用戶端向 Survivable 分支裝置註冊，可能需要這種變更。 如需詳細資訊，請參閱 <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 。



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 的其他軟體

除了作業系統所需的更新之外，Lync Server 2013 還需要作業系統角色、功能和軟體才能運作。 如需在發行拓撲及安裝 Lync Server 2013 之前必須安裝之其他軟體的詳細資訊，請參閱規劃檔中的 [其他軟體需求（Lync Server 2013](lync-server-2013-additional-software-requirements.md) ）。

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>所有伺服器角色所需的其他軟體

在所有伺服器角色上，您也必須確定已安裝 Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5。

此外，在任何要執行 Lync Server 系統管理工具的電腦上，Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5 都是必要的。

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 需要您在您的 Lync Server 拓撲中的每一部電腦上安裝 Windows PowerShell 3.0。 如需安裝 Windows PowerShell 3.0 的詳細資訊，請參閱 [安裝 windows PowerShell 3.0 的 Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)。

<div>


> [!NOTE]
> 在 Windows Server &nbsp; 2008 &nbsp; R2 上使用 SP1，windows PowerShell 命令列介面3.0 無法在安裝 Microsoft .net Framework 4.5 之前安裝。



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

當您在 Windows Server 2012 或 Windows Server 2012 R2 上的伺服器上安裝 Microsoft .NET Framework 4.5，以執行 Lync Server 2013 時，您必須執行一個額外的步驟。 安裝 .NET Framework 4.5 後，請使用伺服器管理員安裝 HTTP 啟用。

**在 Windows Server 2012 或 Windows Server 2012 R2 上安裝 .NET 4.5 HTTP 啟用**

1.  在 [ **開始** ] 功能表上，按一下 [ **程式**]，然後按一下 [系統 **管理工具**]，再按一下 [ **伺服器管理員**]。

2.  在 [伺服器管理員] 的 [ **功能摘要**] 下，選擇 [ **新增功能**]。

3.  展開 **.Net Framework 4.5**。

4.  選取 [ **WCF 啟用** ] （如果尚未選取）。 然後選取 [ **HTTP 啟用**]。

5.  按 **[下一步** ]，然後依照提示完成安裝。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


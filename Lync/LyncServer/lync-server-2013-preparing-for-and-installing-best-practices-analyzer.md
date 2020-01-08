---
title: Lync Server 2013：準備及安裝最佳做法分析程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中準備及安裝最佳做法分析程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

您必須以系統管理員群組成員的身分登入，才能執行本主題中所述的工作。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>最佳做法分析程式安裝的系統需求

若要執行 Lync Server 2013、最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個作業系統的64位版本：

  - Windows Server 2008 R2 Service Pack 1 （SP1）標準作業系統

  - Windows Server 2008 R2 （含 SP1 Enterprise 作業系統）

  - Windows Server 2008 R2 （含 SP1 資料中心作業系統）

  - Windows Server 2012 Datacenter 作業系統

  - Windows Server 2012 標準作業系統

  - Windows Server 2012 企業版作業系統

  - Windows Server 2012 R2 Datacenter 作業系統

  - Windows Server 2012 R2 標準作業系統

  - Windows Server 2012 R2 Enterprise 作業系統

  - Windows 8 作業系統

  - Windows 7 作業系統

電腦也必須執行下列動作：

  - Microsoft .NET Framework 4.5。 針對 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，才能安裝 Lync Server 2013。

  - Lync Server 2013、核心元件。

  - WMI 向後相容性套件。 如需詳細資訊，請參閱在遷移檔中[安裝 WMI 向後相容性套件](install-wmi-backward-compatibility-package.md)。

  - Windows PowerShell 3.0。 如需詳細資訊，請參閱在部署檔中[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md) 。

您可以在有未執行 Lync Server 2013、核心元件或 WMI 向後相容性套件之支援作業系統的電腦上安裝最佳做法分析程式，但您只能在這些電腦上使用最佳做法分析程式來查看報表，而不是以執行掃描。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>選擇要安裝的電腦

我們建議您在專用於 Lync Server 2013 管理的電腦上安裝 Lync Server 2013、最佳做法分析程式。 您可以在執行 Lync Server 2013 的伺服器或執行 Lync Server 2013 系統管理工具的系統管理電腦上安裝該工具。 如果您在執行 Lync Server 的伺服器上安裝該工具，建議您使用該工具只掃描該伺服器。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>安裝最佳做法分析程式

您可以下載適用于 Lync Server 2013 的最佳做法分析[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)程式。

若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft Installer 檔案 RtcBPA，然後依照畫面上的指示進行。 安裝程式檔案的預設\<位置是系統磁碟機\>\\程式檔\\Lync Server 2013\\BPA。

</div>

</div>

<span> </span>

</div>

</div>

</div>


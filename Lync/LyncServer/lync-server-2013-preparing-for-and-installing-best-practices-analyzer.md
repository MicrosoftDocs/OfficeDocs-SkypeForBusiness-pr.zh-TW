---
title: Lync Server 2013：準備及安裝最佳做法分析程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a1ddaff4813035cabc8ca6b7468f1d4d06c93e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506930"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中準備及安裝最佳做法分析程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

您必須以 Administrators 群組成員登入，來執行本主題所說明的工作。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>安裝最佳做法分析程式的系統需求

若要執行 Lync Server 2013，最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個作業系統的64位版本：

  - Windows Server 2008 R2 Service Pack 1 (SP1) Standard 作業系統

  - Windows Server 2008 R2 （含 SP1 Enterprise 作業系統）

  - Windows Server 2008 R2 與 SP1 Datacenter 作業系統

  - Windows Server 2012 Datacenter 作業系統

  - Windows Server 2012 Standard 作業系統

  - Windows Server 2012 企業版作業系統

  - Windows Server 2012 R2 資料中心作業系統

  - Windows Server 2012 R2 Standard 作業系統

  - Windows Server 2012 R2 Enterprise 作業系統

  - Windows 8 作業系統

  - Windows 7 作業系統

該電腦也必須執行下列程式：

  - Microsoft .NET Framework 4.5。 針對 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。

  - Lync Server 2013，核心元件。

  - WMI 回溯相容性套件。 如需詳細資訊，請參閱在遷移檔中 [安裝 WMI 後退相容性套件](install-wmi-backward-compatibility-package.md) 。

  - Windows PowerShell 3.0。 如需詳細資訊，請參閱部署檔中的 [Windows PowerShell 3.0 的 Lync Server 2013 安裝](lync-server-2013-installing-windows-powershell-3-0.md) 。

您可以在支援作業系統的電腦上安裝最佳做法分析程式，但不執行 Lync Server 2013、核心元件或 WMI 回溯相容性套件，但您可以在那些電腦上使用最佳做法分析程式，只查看報告，而不是執行掃描。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>選擇電腦進行安裝

建議您在專用於 Lync Server 2013 管理的電腦上，安裝 Lync Server 2013，最佳做法分析器。 您可以在執行 Lync Server 2013 的伺服器或執行 Lync Server 2013 系統管理工具的系統管理電腦上安裝工具。 [！附注] 如果您在執行 Lync Server 的伺服器上安裝工具，建議您使用工具僅掃描該伺服器。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>安裝最佳做法分析程式

您可以在上下載 Lync Server 2013 的最佳作法分析程式 [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) 。

若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft 安裝程式檔案 RtcBPA.msi，然後依照螢幕上的指示執行。 安裝程式檔案的預設位置是「 \<system drive\> \\ program Files \\ Lync Server 2013 \\ BPA」。

</div>

</div>

<span> </span>

</div>

</div>

</div>


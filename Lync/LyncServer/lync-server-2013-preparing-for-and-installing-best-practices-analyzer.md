---
title: Lync Server 2013： 準備和安裝最佳做法分析程式
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
ms.openlocfilehash: 59bcaca40414c9bd99e451846c0339d0af6e7bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>準備和 Lync Server 2013 中安裝最佳做法分析程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

您必須以 Administrators 群組成員登入，來執行本主題所說明的工作。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>安裝最佳做法分析程式的系統需求

若要執行 Lync Server 2013，最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個下列作業系統的 64 位元版本：

  - Windows Server 2008 R2 Service Pack 1 (SP1) Standard 作業系統

  - Windows Server 2008 R2 Enterprise 作業系統 SP1

  - Windows Server 2008 R2 SP1 Datacenter 作業系統

  - Windows Server 2012 Datacenter 作業系統

  - Windows Server 2012 Standard 作業系統

  - Windows Server 2012 Enterprise 作業系統

  - Windows Server 2012 R2 Datacenter 作業系統

  - Windows Server 2012 R2 Standard 作業系統

  - Windows Server 2012 R2 Enterprise 作業系統

  - Windows 8 作業系統

  - Windows 7 作業系統

該電腦也必須執行下列程式：

  - Microsoft .NET Framework 4.5。 Lync Server 2013 中，您必須手動前安裝 Lync Server 2013 伺服器上安裝 Microsoft.NET Framework 4.5 的 64 位元版本。

  - Lync Server 2013 中，核心元件。

  - WMI 回溯相容性套件。 如需詳細資訊，請參閱移轉文件中的[安裝 WMI 回溯相容性套件](install-wmi-backward-compatibility-package.md)。

  - Windows PowerShell 3.0。 如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中安裝 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md) 。

您可以支援的作業系統與 Lync Server 2013、 核心元件或 WMI 回溯相容性套件，未執行的電腦上安裝最佳做法分析程式，但您可以使用最佳做法分析程式在這些電腦上只檢視報告，不若要執行的掃描。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>選擇電腦進行安裝

我們建議您安裝 Lync Server 2013，專用於 Lync Server 2013 管理的電腦上的最佳做法分析程式。 您可以在執行 Lync Server 2013 或執行 Lync Server 2013 系統管理工具的系統管理電腦的伺服器上安裝此工具。 如果您執行 Lync Server 的伺服器上安裝此工具，我們建議您使用工具來掃描唯有該伺服器。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>安裝最佳做法分析程式

您可以下載在 Lync Server 2013 的最佳做法分析程式[https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)。

若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft 安裝程式檔案 RtcBPA.msi，然後依照螢幕上的指示執行。 安裝程式檔案的預設位置是\<系統磁碟機\>\\Program Files\\Lync Server 2013\\BPA。

</div>

</div>

<span> </span>

</div>

</div>

</div>


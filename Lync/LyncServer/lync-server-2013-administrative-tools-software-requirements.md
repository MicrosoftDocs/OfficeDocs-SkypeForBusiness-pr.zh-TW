---
title: Lync Server 2013：系統管理工具軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Lync Server 2013 中的系統管理工具軟體需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本主題描述除了作業系統需求之外，安裝和使用 Lync Server 2013 系統管理工具所需的軟體。

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4。5

Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3。0

Windows PowerShell 3.0 是執行 Microsoft Lync Server 2013 的任何元件所必需的。 如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer 版本4。5

Lync Server 2013 使用 Windows 安裝程式技術來安裝、卸載及維護各種伺服器角色。 Windows Installer 版本4.5 提供給 Windows Server 作業系統的可發佈元件。 Windows Installer 4.5 隨附 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2，這表示您不需要下載任何執行 Lync Server 2013 之電腦的實用程式。 （Lync Server 2013 只能安裝在運行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的電腦上。）

不過，如果您想要在管理員工作站上安裝 Lync Server 管理命令介面或 Lync Server 拓撲建立器，您可能需要下載 Windows Installer 4.5。 該實用程式隨附于 Windows 7 和 Windows 2008 R2，但不適用於任何舊版的 Windows 作業系統。 您可以從 Microsoft 下載中心下載 Windows Installer 4.5 <http://go.microsoft.com/fwlink/p/?linkid=197395>。

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 瀏覽器外掛程式

Lync Server 2013 [控制台] 是一個以 web 為基礎的工具，需要您安裝最新版的 Microsoft Silverlight 5 瀏覽器外掛程式。 當您啟動 Lync Server 2013 [控制台] 時，如果未安裝這個軟體，或安裝的是舊版，Lync Server 2013 [控制台] 會提示您安裝所需的版本。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的伺服器及工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 中的管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[設定和管理 Lync Server 2013 所需的系統管理員權限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：其他軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 的其他軟體需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

除了伺服器平臺的硬體及作業系統需求之外，Lync Server 2013 還需要在您部署的伺服器上安裝其他軟體。

<div>


> [!NOTE]  
> 如需執行 Lync Server 之伺服器平臺需求的詳細資訊，請參閱 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的伺服器硬體平臺</A>和 lync server 2013 中的 [伺服器<A href="lync-server-2013-server-and-tools-operating-system-support.md">與工具作業系統支援</A>]。 如需用戶端電腦和裝置的系統需求的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的用戶端和裝置規劃</A>。 如需管理工具的軟體需求的詳細資訊，請參閱<A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的系統管理工具軟體需求</A>。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>所有內部伺服器角色所需的其他軟體

本節列出所有內部伺服器角色所需的軟體，這些都是除 Edge 伺服器以外的所有 Lync Server 伺服器角色。 Edge 伺服器與邊緣池的需求將在本主題的 [**其他適用于 Edge 伺服器的軟體**] 底下列出。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3。0

每個執行 Lync Server 2013 的伺服器都必須安裝正確的 Windows PowerShell 3.0 版本。 如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4。5

Lync Server 在所有內部伺服器角色以及任何您要執行 Lync Server 系統管理工具或 Microsoft Lync Server 2013 的電腦上，都需要 Microsoft .NET Framework 4.5，這是規劃工具。 針對 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，才能安裝 Lync Server 2013。 若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 架構[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>在執行 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4。5

當您在將執行 Lync Server 2013 和 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4.5 時，您必須執行一個額外的步驟。 安裝 .NET Framework 4.5 之後，請使用伺服器管理員來安裝 HTTP 啟用。

**在 Windows Server 2012 上安裝 .NET 4.5 HTTP 啟用**

1.  從 [**開始**] 功能表，按一下 [**程式**]，然後按一下 [**管理工具**]，再按一下 [**伺服器管理員**]。

2.  在 [伺服器管理員] 的 [**功能摘要**] 底下，選擇 [**新增功能**]。

3.  展開 [ **.Net Framework 4.5**]。

4.  選取 [ **WCF 啟用**] （如果尚未選取的話）。 然後選取 [ **HTTP 啟用**]。

5.  按一下 **[下一步**]，然後依照提示完成安裝。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows 身分識別基礎

在 Lync Server 2013 中的**Windows 身分識別基礎**需要安裝 Windows 身分識別基礎，才能支援伺服器到伺服器驗證案例。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 身分識別基礎。 從下列清單選取您的伺服器作業系統：

  - Windows server 2008 R2 For Windows Server 2008 R2，您可以檢查是否已將它安裝在您的電腦上。 若要這樣做，請移至 [**新增/移除程式**]、[**查看已安裝的更新**]，然後在 [ **windows** ] 底下看到 [專案**windows 身分識別基礎（KB974405）**]。 如需安裝 Windows 身分識別基礎的詳細[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。

  - Windows server 2012 For Windows Server 2012，您可以使用**伺服器管理員**來安裝 Windows 身分識別基礎。 在伺服器管理員 [**新增角色與功能] 嚮導**中，選取 [**功能**]。 從清單中選取 [ **Windows 身分識別基礎 3.5** ]。 按一下 **[下一步]**，然後按一下 [**安裝**]。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>適用于所有前端伺服器和標準版伺服器的其他軟體

所有前端伺服器和標準版伺服器也都必須在特定的模組中執行網際網路資訊服務（IIS）。 此外，部署會議、通話駐留應用程式、公告或回應群組的所有前端伺服器和標準版伺服器，都必須執行 Windows Media 格式執行時間。

<div>

## <a name="internet-information-services-iis"></a>網際網路資訊服務（IIS）

前端伺服器和標準版伺服器必須執行網際網路資訊服務（IIS），並附帶下列模組：

  - 靜態內容

  - 預設檔

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API （ISAPI）延伸

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 診斷

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - 動態內容壓縮

  - IIS 管理主控台

  - IIS 管理腳本與工具

  - 匿名驗證（預設會在安裝 IIS 時安裝）。）

  - 用戶端憑證對應驗證

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media 格式執行時間與 Windows 桌上出版體驗

**Windows 桌面體驗**部署會議所需的所有前端伺服器和標準版伺服器都必須安裝 Windows Media 執行時間，但 Windows Server 2012 （除了 windows 桌上出版體驗之外）還會安裝。 Windows Server 2012 需要 Microsoft 媒體基礎。 您必須具備 Windows Media 格式執行時間，才能執行通話駐留、宣告及回應群組應用程式的 Windows Media 音訊（.wma）檔案，以便在公告和音樂中播放。

我們建議您先安裝 Windows 桌面體驗，然後再安裝 Lync Server 2013。 如果 Lync Server 2013 在伺服器上找不到這個軟體，系統會提示您安裝它，然後您必須重新開機伺服器才能完成安裝。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>在 Windows Server 2012 上執行的前端伺服器和標準版伺服器的其他軟體

前端伺服器需要 .NET 3.5 （預設不會安裝在 Windows Server 2012 上）。 若要安裝，請將您的 Windows Server 2012 安裝媒體放在磁碟機 D 中，並輸入以下內容：

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

如需在執行 Windows Server 2012 的伺服器上安裝 .NET 3.5 的詳細資訊，請參閱「Microsoft .NET Framework <https://go.microsoft.com/fwlink/p/?linkid=275032>3.5 部署考慮」。

</div>

<div>

## <a name="additional-software-for-directors"></a>其他董事版軟體

控制器必須執行網際網路資訊服務（IIS），並提供下列模組：

  - 靜態內容

  - 預設檔

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API （ISAPI）延伸

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 診斷

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - IIS 管理主控台

  - IIS 管理腳本與工具

  - 匿名驗證（預設會在安裝 IIS 時安裝）。）

  - 用戶端憑證對應驗證

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>持續聊天前端伺服器的其他軟體

持續聊天前端伺服器必須執行訊息佇列（也稱為 MSMQ），這是 Windows Server 的元件。

如需啟用 MSMQ 的詳細資訊，請[按一下這裡。](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>其他適用于 Edge 伺服器的軟體

Edge 伺服器需要下列軟體：

  - 每個執行 Lync Server 2013 的伺服器都必須安裝正確的 Windows PowerShell 3.0 版本。 如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

  - Lync Server 需要 Microsoft .NET Framework 4.5。 在 Windows Server 2008 R2 上安裝的 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，然後才能安裝 Lync Server 2013。 若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 架構[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - 在 Lync Server 2013 中的**Windows 身分識別基礎**需要安裝 Windows 身分識別基礎，才能支援伺服器到伺服器驗證案例。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 身分識別基礎。 從下列清單選取您的伺服器作業系統：
    
      - Windows server 2008 R2 For Windows Server 2008 R2，您可以檢查是否已將它安裝在您的電腦上。 若要這樣做，請移至 [**新增/移除程式**]、[**查看已安裝的更新**]，然後在 [ **windows** ] 底下看到 [專案**windows 身分識別基礎（KB974405）**]。 如需安裝 Windows 身分識別基礎的詳細[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。
    
      - Windows server 2012 For Windows Server 2012，您可以使用**伺服器管理員**來安裝 Windows 身分識別基礎。 在伺服器管理員 [**新增角色與功能] 嚮導**中，選取 [**功能**]。 從清單中選取 [ **Windows 身分識別基礎 3.5** ]。 按一下 **[下一步]**，然後按一下 [**安裝**]。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>不要在媒體伺服器上安裝多層次通訊端提供者

請勿在任何前端伺服器或獨立的中繼伺服器上安裝任何 Microsoft 網際網路安全性與加速（ISA） Server 用戶端軟體或任何其他 Winsock 層次服務提供者（LSP）軟體。 安裝這個軟體可能會導致媒體流量較差的效能。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的系統管理工具軟體需求](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


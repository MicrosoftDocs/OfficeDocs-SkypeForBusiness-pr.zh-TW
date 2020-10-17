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
ms.openlocfilehash: 9a4a0c2e200c779d87a13c08eada968b27a7447f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521230"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 的其他軟體需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

除了伺服器平臺的硬體和作業系統需求之外，Lync Server 2013 還需要在您部署的伺服器上安裝其他軟體。

<div>


> [!NOTE]  
> 如需執行 Lync Server 之伺服器平臺需求的詳細資訊，請參閱 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的伺服器硬體平臺</A> 和 <A href="lync-server-2013-server-and-tools-operating-system-support.md">伺服器及工具作業系統支援（lync server 2013</A>）。 如需用戶端電腦和裝置之系統需求的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-clients-and-devices.md">規劃 Lync Server 2013 中的用戶端和裝置</A> 。 如需系統管理工具軟體需求的詳細資訊，請參閱 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的系統管理工具軟體需求</A>。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>所有內部伺服器角色所需的其他軟體

本節列出所有內部伺服器角色所需的軟體，也就是除 Edge Server 之外所有的 Lync Server server 角色。 Edge server 和 Edge 集區的其他軟體會列在本主題稍後的 **其他適用于 Edge server 的軟體**。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

每一部執行 Lync Server 2013 的伺服器必須已安裝正確的 Windows PowerShell 3.0 版本。 如需詳細資訊，請參閱 [安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 需要 Microsoft .NET Framework 4.5 在所有內部伺服器角色上，以及您要執行 Lync Server 系統管理工具或 Microsoft Lync Server 2013 的任何電腦上，規劃工具。 針對 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。 若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 Framework，網址是 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>在執行 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4。5

當您在將執行 Lync Server 2013 和 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4.5 時，您必須執行一個額外的步驟。 安裝 .NET Framework 4.5 後，請使用伺服器管理員安裝 HTTP 啟用。

**在 Windows Server 2012 上安裝 .NET 4.5 HTTP 啟用**

1.  在 [ **開始** ] 功能表上，按一下 [ **程式**]，然後按一下 [系統 **管理工具**]，再按一下 [ **伺服器管理員**]。

2.  在 [伺服器管理員] 的 [ **功能摘要**] 下，選擇 [ **新增功能**]。

3.  展開 **.Net Framework 4.5**。

4.  選取 [ **WCF 啟用** ] （如果尚未選取）。 然後選取 [ **HTTP 啟用**]。

5.  按 **[下一步** ]，然後依照提示完成安裝。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013 中的**Windows Identity foundation**需要安裝 Windows identity foundation，才能支援伺服器的伺服器驗證案例。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 識別基礎。 從下列清單中選取您的伺服器作業系統：

  - Windows server 2008 R2 For Windows Server 2008 R2，您可以查看是否已安裝在電腦上。 若要這麼做，請移至 [ **新增/移除程式**]、[ **查看已安裝的更新**]，然後在 [ **windows** ] 下的 [專案 **windows Identity Foundation (KB974405) **中查看。 如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。

  - Windows server 2012 For Windows Server 2012，您可以使用 **伺服器管理員** 安裝 Windows Identity Foundation。 在 [伺服器管理員 **新增角色與功能] 嚮導**中，選取 [ **功能**]。 從清單中選取 [ **Windows Identity Foundation 3.5** ]。 按 **[下一步]**，然後按一下 [ **安裝**]。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>所有前端伺服器和 Standard Edition Server 的其他軟體

所有前端伺服器和 Standard Edition server 也必須執行 Internet Information Services (IIS) 與某些模組。 此外，部署會議、通話駐留應用程式、宣告或回應群組的所有前端伺服器和 Standard Edition 伺服器，都必須執行 Windows Media Format Runtime。

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

前端伺服器和 Standard Edition 伺服器必須使用下列模組執行 Internet Information Services (IIS) ：

  - 靜態內容

  - 預設文件

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API (ISAPI) 擴充

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 跟蹤

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - 動態內容壓縮

  - IIS 管理主控台

  - IIS 管理指令碼與工具

  - 匿名驗證 (在安裝 IIS 時預設會安裝此功能。 ) 

  - 用戶端憑證對應驗證

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime 和 Windows 桌面體驗

**Windows 桌面體驗** 所有要部署會議的前端伺服器和 Standard Edition 伺服器都必須已安裝 Windows Media Format Runtime，但 Windows Server 2012 除外，也會安裝 windows 桌面體驗的一部分。 Windows Server 2012 需要 Microsoft Media Foundation。 Windows Media Format Runtime 是執行 Windows Media Audio () 檔案，可讓通話駐留、宣告及回應群組應用程式對宣告和音樂播放。

建議您先安裝 Windows 桌面體驗，再安裝 Lync Server 2013。 如果 Lync Server 2013 在伺服器上找不到此軟體，它會提示您安裝它，然後您必須重新開機伺服器以完成安裝。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>在 Windows Server 2012 上執行的前端伺服器和 Standard Edition 伺服器的其他軟體

前端伺服器需要 .NET 3.5，這不會在 Windows Server 2012 上預設安裝。 若要安裝，請將 Windows Server 2012 安裝媒體置於磁碟機 D 中，並輸入下列專案：

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

如需在執行 Windows Server 2012 的伺服器上安裝 .NET 3.5 的詳細資訊，請參閱 at 中的「Microsoft .NET Framework 3.5 部署考慮」 <https://go.microsoft.com/fwlink/p/?linkid=275032> 。

</div>

<div>

## <a name="additional-software-for-directors"></a>Director 的其他軟體

Director 必須使用下列模組執行 Internet Information Services (IIS) ：

  - 靜態內容

  - 預設文件

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API (ISAPI) 擴充

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 跟蹤

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - IIS 管理主控台

  - IIS 管理指令碼與工具

  - 匿名驗證 (在安裝 IIS 時預設會安裝此功能。 ) 

  - 用戶端憑證對應驗證

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>適用于持久聊天前端伺服器的其他軟體

Persistent Chat 前端伺服器必須執行郵件佇列 (也稱為 MSMQ) ，也就是 Windows Server 的元件。

如需啟用 MSMQ 的資訊，請 [按一下這裡。](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>其他 Edge Server 軟體

Edge Server 需要下列軟體：

  - 每一部執行 Lync Server 2013 的伺服器必須已安裝正確的 Windows PowerShell 3.0 版本。 如需詳細資訊，請參閱 [安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

  - Lync Server 需要 Microsoft .NET Framework 4.5。 針對安裝在 Windows Server 2008 R2 上的 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。 若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 Framework，網址是 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013 中的**Windows Identity foundation**需要安裝 Windows identity foundation，才能支援伺服器的伺服器驗證案例。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 識別基礎。 從下列清單中選取您的伺服器作業系統：
    
      - Windows server 2008 R2 For Windows Server 2008 R2，您可以查看是否已安裝在電腦上。 若要這麼做，請移至 [ **新增/移除程式**]、[ **查看已安裝的更新**]，然後在 [ **windows** ] 下的 [專案 **windows Identity Foundation (KB974405) **中查看。 如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。
    
      - Windows server 2012 For Windows Server 2012，您可以使用 **伺服器管理員** 安裝 Windows Identity Foundation。 在 [伺服器管理員 **新增角色與功能] 嚮導**中，選取 [ **功能**]。 從清單中選取 [ **Windows Identity Foundation 3.5** ]。 按 **[下一步]**，然後按一下 [ **安裝**]。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>不要在媒體伺服器上安裝分層通訊端提供者

請勿在任何前端伺服器或獨立轉送伺服器上安裝任何 Microsoft Internet 安全性和加速 (ISA) Server 用戶端軟體或任何其他 Winsock 分層服務提供者 (LSP) 軟體。 安裝此軟體可能會導致媒體流量效能降低。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的系統管理工具軟體需求](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


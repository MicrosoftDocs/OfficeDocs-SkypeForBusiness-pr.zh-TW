---
title: Lync Server 2013：疑難排解 Lync Server 2013 [控制台]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 [控制台] 的疑難排解

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

本主題提供的資訊和程式可協助您疑難排解 Lync Server 2013 [控制台] 的存取權。

<div>

## <a name="internet-browser-requirements"></a>網際網路瀏覽器的需求

Lync Server 控制台需要安裝 Microsoft Silverlight 瀏覽器外掛程式版本4.0.50524.0 或最新版本。 如果未安裝 Silverlight，或安裝的是舊版版本，請依照訊息中的指示安裝所需的版本。

<div>


> [!NOTE]  
> Lync Server [控制台] 的其他軟體需求適用于 Lync Server [控制台] 以及所有其他 Lync Server 2013 系統管理工具可安裝的作業系統。 如需詳細資訊，請參閱支援檔中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 中的伺服器和工具作業系統支援</A>。



</div>

如果您的網際網路瀏覽器由於安全考慮而封鎖 Silverlight 的安裝，請將開啟 Lync Server [控制台] 的統一資源定位器（URL）新增到信任的網站清單中。 在 Internet Explorer 安全性設定中，請確定 **[執行 ActiveX 控制項與外掛程式]** 已設定為 [**啟用**]。 如需詳細資訊[http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)，請參閱。 此外，請確定瀏覽器已設定為使用 SSL 3.0。

如果 Internet 瀏覽器已設定為使用 proxy 伺服器，請確認瀏覽器已設定為對自動偵測為內部網站的網站略過 proxy 伺服器。 或者，在 proxy 伺服器設定中，將位址新增到瀏覽器的例外清單中。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>管理存取 URL 的 DNS 記錄與證書需求

如果您已將簡單的 URL 設定為 access Lync Server 控制台，請確定您也已設定靜態網域名稱系統（DNS）主機（A）資源記錄及證書，以使用該管理存取 URL。 如果您隨時變更基底 URL，請確定變更會反映在適當的 DNS 記錄和憑證中，並且您在每個控制器和前端伺服器上執行*Enable CsComputer*來登錄變更。 如需詳細資訊，請參閱規劃檔中的下列主題：

  - [在 Lync Server 2013 中規劃簡單 URL](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中簡單 URL 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

如需設定管理存取 URL 的逐步程式，請參閱在部署檔中[編輯或設定 Lync Server 2013 中的簡單 url](lync-server-2013-edit-or-configure-simple-urls.md) 。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>網際網路資訊服務（IIS）需求

Lync Server [控制台] 是需要 Internet Information Services （IIS）的 Lync Server 2013 元件之一。 特別是，請確定已啟用 HTTP 重新導向及 Windows 驗證功能，且萬維網發佈服務（W3SVC）正在執行。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>全球廣發佈服務（Windows 服務）相依性

當萬維網發佈服務停止時，您無法存取 Lync Server [控制台]。 您可以使用 Windows Services Microsoft 管理主控台（MMC）重新開機服務。

**啟動 World Wide Web 發佈服務**

1.  登入安裝萬維網發佈服務的電腦，這是網際網路資訊服務（IIS）的一部分。

2.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [**服務**]。

3.  以滑鼠右鍵按一下 [**萬維網發佈服務**]，然後按一下 [**開始**]。

</div>

<div>

## <a name="application-pool-mode"></a>應用程式池模式

設定 IIS，讓 CsManagementAppPool 應用程式池使用 Network Service 帳戶做為其處理模型身分識別。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>使用者權利與許可權

您必須使用是 CsAdministrator 群組成員的網域帳戶，或使用您已委派使用者權利和許可權的帳戶登入 Lync Server [控制台]。 您無法使用本機電腦帳戶登入 Lync Server [控制台]。 如需透過角色式存取控制（RBAC）委派管理工作的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的角色式存取控制規劃](lync-server-2013-planning-for-role-based-access-control.md)。

如果您使用簡單的 URL 來存取 Lync Server 控制台，請確定網頁伺服器已新增至 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 群組。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


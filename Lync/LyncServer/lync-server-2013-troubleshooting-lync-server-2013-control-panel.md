---
title: 'Lync Server 2013: Troubleshooting Lync Server 2013 控制台'
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
ms.openlocfilehash: 07e670dc0871490e513023d3276ad80126be173b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>疑難排解 Lync Server 2013 控制台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-07-28_

本主題提供的資訊和程序，可協助您疑難排解存取 Lync Server 2013 控制台。

<div>

## <a name="internet-browser-requirements"></a>網際網路瀏覽器需求

Lync Server 控制台需要已安裝 Microsoft Silverlight 瀏覽器外掛程式版本 4.0.50524.0 或最新版本。 如果未安裝 Silverlight 或安裝更早的版本，請依照下列訊息即可安裝必要的版本中的指示。

<div>


> [!NOTE]  
> Lync Server 控制台的其他軟體需求適用於 Lync Server Control Panel 及所有其他 Lync Server 2013 系統管理工具可以安裝所在的作業系統。 如需詳細資訊，請參閱支援文件中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 中的伺服器和工具作業系統支援</A>。



</div>

如果您網際網路瀏覽器封鎖安裝 Silverlight 因安全性考量而新增統一資源定位器 (URL)，會開啟 Lync Server Control Panel 的信任網站清單。 在 Internet Explorer 安全性設定中，確定 [執行 ActiveX 控制項及外掛程式]**** 設為 [已啟用]****。 如需詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)。 此外，請確定瀏覽器設定為使用 SSL 3.0。

如果網際網路瀏覽器設定為使用 Proxy 伺服器，請確認瀏覽器針對自動偵測為內部站台的站台，設定為略過 Proxy 伺服器。或者，在 Proxy 伺服器組態設定中，將位址新增至瀏覽器的例外清單。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>系統管理存取 URL 的 DNS 記錄及憑證需求

如果您設定簡單 URL 來存取 Lync Server Control Panel，請確定您也設定靜態的網域名稱系統 (DNS) 主機 (A) 資源記錄和憑證必須使用該系統管理存取 URL。 如果您在任何時間變更的基底 URL，請確定此變更會反映在適當的 DNS 記錄和憑證，而且您執行*Enable-cscomputer* ，以登錄變更每個 Director 與前端伺服器上。 如需詳細資訊，請參閱＜規劃＞文件中的下列主題：

  - [規劃 Lync Server 2013 中的簡單 Url](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [適用於 Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

若要設定系統管理存取 URL 的逐步程序，請參閱部署文件中的[編輯或設定在 Lync Server 2013 中的簡單 Url](lync-server-2013-edit-or-configure-simple-urls.md) 。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 需求

Lync Server Control Panel 是一個需要網際網路資訊服務 (IIS) 的 Lync Server 2013 的元件。 特別是，請確定 HTTP 重新導向和 Windows 驗證功能已啟用，而且 World Wide Web Publishing 服務 (W3SVC) 正在執行。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Publishing Service (Windows 服務) 相依性

World Wide Web Publishing 服務停止時，您不能存取 Lync Server Control Panel。 您可以使用 Windows Services Microsoft Management Console (MMC) 來重新啟動服務。

**啟動 World Wide Web Publishing 服務**

1.  World Wide Web Publishing 服務一部分的網際網路資訊服務 (IIS) 的安裝所在的電腦登入。

2.  依序按一下 [開始]****、[系統管理工具]**** 和 [服務]****。

3.  用滑鼠右鍵按一下 [World Wide Web Publishing 服務]****，然後按一下 [啟動]****。

</div>

<div>

## <a name="application-pool-mode"></a>應用程式集區模式

設定 IIS，讓 CsManagementAppPool 應用程式集區使用網路服務帳戶做為其處理序模型身分識別。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>使用者權限

您必須登入 Lync Server Control Panel 使用網域帳戶屬於 CsAdministrator 群組的成員，或使用您已委派使用者權利和權限的帳戶。 您無法使用本機電腦帳戶來登入 Lync Server Control Panel。 如需有關委派系統管理工作，透過角色型存取控制 (RBAC) 的詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md)。

如果您使用簡單 URL 來存取 Lync Server Control Panel，確保伺服器已新增至 RTCUniversalServerAdmins 及 RTCUniversalUserAdmins 群組的網頁。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


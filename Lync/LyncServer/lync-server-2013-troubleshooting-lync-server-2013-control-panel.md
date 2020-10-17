---
title: Lync Server 2013： Lync Server 2013 控制台疑難排解
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
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535930"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a>疑難排解 Lync Server 2013 控制台

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

本主題提供的資訊和程式可協助您疑難排解 Lync Server 2013 控制台的存取。

<div>

## <a name="internet-browser-requirements"></a>網際網路瀏覽器需求

Lync Server 控制台要求安裝 Microsoft Silverlight 瀏覽器外掛程式版本4.0.50524.0 或最新版本。 若未安裝 Silverlight 或已安裝舊版，請依照訊息中的指示安裝必要的版本。

<div>


> [!NOTE]  
> Lync Server 控制台的其他軟體需求，適用于可安裝 Lync Server 控制台和所有其他 Lync Server 2013 系統管理工具的作業系統。 如需詳細資訊，請參閱支援檔中的 <A href="lync-server-2013-server-and-tools-operating-system-support.md">伺服器和工具作業系統支援（Lync Server 2013</A> ）。



</div>

如果您的網際網路瀏覽器因安全性考慮而封鎖安裝 Silverlight，請將開啟 Lync Server 控制台的統一資源定位器 (URL) 新增至受信任的網站清單。 在 Internet Explorer 安全性設定中，確定 [執行 ActiveX 控制項及外掛程式]**** 設為 [已啟用]****。 如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 。 此外，請確定瀏覽器設定為使用 SSL 3.0。

如果網際網路瀏覽器設定為使用 Proxy 伺服器，請確認瀏覽器針對自動偵測為內部站台的站台，設定為略過 Proxy 伺服器。或者，在 Proxy 伺服器組態設定中，將位址新增至瀏覽器的例外清單。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>系統管理存取 URL 的 DNS 記錄及憑證需求

如果您設定了簡易 URL 來存取 Lync Server 控制台，請確定您也已設定靜態網域名稱系統 (DNS) 主機 (使用該管理存取 URL 所需的) 資源記錄和憑證。 如果您隨時變更基底 URL，請確定變更會反映在適當的 DNS 記錄和憑證中，並且在每個 Director 和前端伺服器上執行 *Enable-CsComputer* 以登錄變更。 如需詳細資訊，請參閱＜規劃＞文件中的下列主題：

  - [在 Lync Server 2013 中規劃簡易 URLs](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 中簡易 URLs 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

如需設定管理存取 URL 的逐步程式，請參閱部署檔中的在 [Lync Server 2013 中編輯或設定簡單 URLs](lync-server-2013-edit-or-configure-simple-urls.md) 。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 需求

Lync Server 控制台是 Lync Server 2013 的其中一個元件，需要 Internet Information Services (IIS) 。 特別是，請確定 HTTP 重新導向和 Windows 驗證功能已啟用，而且 World Wide Web Publishing 服務 (W3SVC) 正在執行。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Publishing Service (Windows 服務) 相依性

停止 World Wide Web 發佈服務後，就無法存取 Lync Server 控制台。 您可以使用 Windows Services Microsoft Management Console (MMC) 來重新啟動服務。

**啟動 World Wide Web Publishing 服務**

1.  以網際網路資訊服務 (IIS) 的一部分，登入安裝 World Wide Web 發佈服務的電腦。

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

您必須使用屬於 CsAdministrator 群組成員的網域帳戶，或是使用已委派使用者權限的帳戶，登入 Lync Server 控制台。 您無法使用本機電腦帳戶登入 Lync Server 控制台。 如需透過以角色為基礎的存取控制委派系統管理工作的詳細資訊 (RBAC) ，請參閱規劃檔中的 [規劃 Lync Server 2013 中的角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md) 。

如果您使用簡易 URL 來存取 Lync Server 控制台，請確定網頁伺服器已新增至 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 群組。

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


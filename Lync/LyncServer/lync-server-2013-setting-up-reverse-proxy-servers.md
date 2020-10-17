---
title: Lync Server 2013：設定反向 proxy 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521810"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>設定 Lync Server 2013 的反向 proxy 伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-08_

針對 Microsoft Lync Server 2013 Edge Server 部署，外部用戶端必須使用周邊網路反向 proxy，才能存取「Director」和使用者主集區的 [Office 通訊伺服器) 中稱為 *Web 元件* (的 Lync Server 2013 web 服務]。 有些需要透過反向 Proxy 進行外部存取的功能包含下列項目：

  - 讓外部使用者能夠下載會議的內容。

  - 讓外部使用者能夠擴充通訊群組。

  - 讓遠端使用者能夠從通訊錄服務下載檔案。

  - 存取 Lync Web App 用戶端。

  - 存取 [電話撥入式會議設定] 網頁。

  - 讓外部裝置能夠連線至裝置更新 Web 服務並取得更新。

  - 讓行動應用程式能夠自動探索和使用行動性 (Mcx) URLs 從網際網路。

  - 啟用 Lync 2013 用戶端、Lync Windows Store 應用程式和 Lync 2013 行動用戶端，以找出 Lync 探索 (自動探索) URLs 和使用整合通訊 Web API (UCWA) 。

我們建議將您的 HTTP 反向 Proxy 設定成發行所有集區中的所有 Web 服務。 發佈 HTTPs://ExternalFQDN/ \* 發佈所有集區的 IIS 虛擬目錄。 您組織中的每一個 Standard Edition Server、前端集區或 Director 或 Director 集區都需要有一個發行規則。

此外，您必須發佈簡易 URLs。 如果組織有 Director 或 Director 集區，HTTP 反向 proxy 會偵聽 HTTP/HTTPS 對簡單 URLs 的要求，並將其代理到 Director 或 Director 集區上的外部 Web 服務虛擬目錄。 若尚未部署 Director，您必須指定一個集區，以處理簡單 URLs 的要求。  (如果這不是使用者的主集區，則會將它們重新導向至使用者主集區上的 Web 服務) 。 簡單的 URLs 可以透過專用的 web 發行規則來處理，也可以將其新增到 Director 之網頁發行規則的公用名稱。 您也需要發佈外部自動探索服務 URL。

您可以使用 Microsoft Forefront 威脅管理閘道2010、Microsoft Internet 安全性和加速度 (ISA) Server 2006 SP1 或 Internet Information Server 7.0、7.5 或8.0，且應用程式要求路由 (IIS ARR) 做為反向 proxy。 這一節中的詳細步驟說明如何設定 Forefront Threat Management Gateway 2010，而且用於設定 ISA Server 2006 的步驟幾乎相同。 也會為 IIS ARR 提供指導方針。 如果您使用其他的反向 Proxy，請參閱該產品的文件，並將此處定義的需求對應至其他反向 Proxy 中的關聯功能。

<div>


> [!IMPORTANT]  
> Internet Information Server 應用程式要求路由 (IIS ARR) 是針對 Lync Server 2010 和 Lync Server 2013 實施反向 proxy 的經過完整測試及支援的選項。 在2012年11月，Microsoft 未 ForeFront 威脅管理閘道2010或 TMG 的授權銷售。 TMG 仍是完全支援的產品，仍然可在協力廠商銷售的裝置上銷售。 此外，許多協力廠商硬體負載平衡器和防火牆都提供反向 proxy 支援。 如需提供反向 proxy 功能的硬體負載平衡器和防火牆，請諮詢您的廠商，以取得如何設定其產品以提供 Lync Server 的反向 proxy 支援的特定指示。 您也可以查看已將產品的檔提交至 Microsoft 的協力廠商。 支援由協力廠商提供，以供其解決方案使用。 若要查看提供解決方案時使用中的協力廠商，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 的基礎結構限定</A>。



</div>

下列主題及程式使用 Forefront 威脅管理閘道2010和 IIS ARR 做為部署及設定程式的基礎。

  - [設定 Lync Server 2013 的 web 伺服器陣列 Fqdn](lync-server-2013-configure-web-farm-fqdns.md)

  - [在 Lync Server 2013 中設定網路介面卡](lync-server-2013-configure-network-adapters.md)

  - [在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [在 Lync Server 2013 中設定單一內部集區的 web 發佈規則](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [在 Lync Server 2013 中驗證或設定 IIS 虛擬目錄上的驗證和憑證](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中驗證是否透過您的反向 proxy 進行存取](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>開始之前

若要順利將 Forefront Threat Management Gateway 2010 部署成您的反向 Proxy，您必須安裝及設定伺服器，並使用 Forefront Threat Management Gateway 2010 文件中定義的先決條件和硬體需求。 請參閱下列主題設定為正確地設定硬體，並在伺服器上安裝 Forefront 威脅管理閘道2010，再繼續進行。

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 硬體建議](https://go.microsoft.com/fwlink/?linkid=291293)

若要將 IIS ARR 成功部署為反向 proxy，請參閱下列主題以設定硬體和必要條件軟體。

  - <span></span>  
    若要在 Windows Server 2008 或 Windows Server 2008 R2 上安裝 IIS，請參閱 [在 Windows server 2008 或 Windows server 2008 r2 上安裝 iis 7](https://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    若要在 Windows Server 2012 上安裝 IIS，請參閱[在 Windows server 2012 上安裝 iis 8](https://go.microsoft.com/fwlink/?linkid=291297) 。

  - <span></span>  
    若要在 Windows Server 2012 R2 上安裝 IIS，請參閱 [在 Windows server 2012 R2 上安裝 iis 8.5](https://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    若要下載 IIS 的應用程式要求路由分機分機，請依照[應用程式要求路由傳送第 2.5](https://go.microsoft.com/fwlink/?linkid=291298)版的指示下載

  - <span></span>  
    若要安裝 ARR，請參閱[安裝應用程式要求路由第2版](https://go.microsoft.com/fwlink/?linkid=291299)時的指示
    
    <div>
    

    > [!NOTE]  
    > 目前發佈的指令是用於 ARR 2.0。 若要安裝分機號碼，這兩種版本沒有區別。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


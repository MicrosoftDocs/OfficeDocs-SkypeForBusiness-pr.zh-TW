---
title: Lync Server 2013： 設定被動驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a50cb75bdf833468d6974b9ddce1b282c1872d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="536cb-102">設定 Lync Server 2013 被動驗證</span><span class="sxs-lookup"><span data-stu-id="536cb-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="536cb-103">_**上次修改主題：** 2013年-07-11_</span><span class="sxs-lookup"><span data-stu-id="536cb-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="536cb-104">下節說明如何設定 Lync Server 2013 累計更新： 7 月 2013 以支援被動驗證。</span><span class="sxs-lookup"><span data-stu-id="536cb-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="536cb-105">雙因素驗證已啟用 Lync 之使用者啟用之後，必須使用實體或虛擬智慧卡及有效的 pin 碼登入 Lync 2013 累計更新： 7 月 2013年用戶端。</span><span class="sxs-lookup"><span data-stu-id="536cb-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="536cb-106">強烈建議客戶啟用被動驗證的登錄器，並在服務層級的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="536cb-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="536cb-107">如果被動驗證已啟用的登錄器，並在全域層級的 Web 服務，可能會導致整個組織的驗證失敗的使用者未登入 Lync 2013 累計更新： 7 月 2013年用戶端桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="536cb-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="536cb-108">Web 服務組態</span><span class="sxs-lookup"><span data-stu-id="536cb-108">Web Service Configuration</span></span>

<span data-ttu-id="536cb-109">下列步驟說明如何建立自訂 web 服務設定 Director、 Enterprise 集區和 Standard Edition server，將啟用被動驗證。</span><span class="sxs-lookup"><span data-stu-id="536cb-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="536cb-110">**若要建立自訂 web 服務組態**</span><span class="sxs-lookup"><span data-stu-id="536cb-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="536cb-111">登入您 Lync Server 2013 累計更新： 7 月 2013年使用 Lync 系統管理員帳戶的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="536cb-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="536cb-112">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="536cb-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="536cb-113">從 Lync Server 管理命令介面命令列，建立新的 Web 服務組態的每個 Director、 Enterprise 集區和 Standard Edition 伺服器，將啟用被動驗證，藉由執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="536cb-114">WsFedPassiveMetadataUri FQDN 的值是同盟服務名稱的 AD FS 2.0 伺服器。</span><span class="sxs-lookup"><span data-stu-id="536cb-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="536cb-115">同盟服務名稱值可以中找到的 AD FS 2.0 管理主控台<STRONG>服務</STRONG>上從功能窗格中按一下滑鼠右鍵，然後選取 [<STRONG>編輯同盟服務內容</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="536cb-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="536cb-116">確認 [UseWsFedPassiveAuth] 和 [WsFedPassiveMetadataUri 值已正確設定，藉由執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="536cb-117">用戶端，被動驗證是 webticket 驗證的最低慣用的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="536cb-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="536cb-118">所有 Director、 Enterprise 集區和 Standard Edition server，將啟用被動驗證，其他所有驗證類型必須停都都用 Lync Web 服務中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="536cb-119">確認所有其他驗證類型有已成功停用來執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="536cb-120">Proxy 組態</span><span class="sxs-lookup"><span data-stu-id="536cb-120">Proxy Configuration</span></span>

<span data-ttu-id="536cb-121">Lync Web 服務停用憑證驗證時，Lync 用戶端會使用佳的驗證類型，例如 Kerberos 或 ntlm 驗證，來對登錄器服務進行驗證。</span><span class="sxs-lookup"><span data-stu-id="536cb-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="536cb-122">仍然需要允許擷取 webticket Lync 用戶端憑證驗證，不過，Kerberos 及 NTLM 必須停用的登錄器服務。</span><span class="sxs-lookup"><span data-stu-id="536cb-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="536cb-123">下列步驟說明如何建立自訂的 proxy 設定 Edge 集區、 Enterprise 集區和 Standard Edition server，將啟用被動驗證。</span><span class="sxs-lookup"><span data-stu-id="536cb-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="536cb-124">**若要建立自訂的 proxy 設定**</span><span class="sxs-lookup"><span data-stu-id="536cb-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="536cb-125">從 Lync Server 管理命令介面命令列，建立新的 proxy 設定每個 Lync Server 2013 的累計更新： 7 月 2013年將啟用被動驗證，藉由執行的 Edge 集區、 Enterprise 集區和 Standard Edition server下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="536cb-126">確認所有其他 proxy 驗證類型有已成功停用來執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="536cb-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>


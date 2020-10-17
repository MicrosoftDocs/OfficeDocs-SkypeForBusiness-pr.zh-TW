---
title: Lync Server 2013：設定被動驗證
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
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532490"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="8bfb7-102">設定 Lync Server 2013 被動驗證</span><span class="sxs-lookup"><span data-stu-id="8bfb7-102">Configuring Lync Server 2013 passive authentication</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bfb7-103">_**主題上次修改日期：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="8bfb7-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="8bfb7-104">下列章節說明如何設定具有累積更新的 Lync Server 2013：7月2013以支援被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="8bfb7-105">一旦啟用，啟用兩個要素驗證的 Lync 使用者將需要使用實體或虛擬智慧卡和有效 PIN 碼，使用 Lync 2013 搭配累計更新來登入：7月2013用戶端。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8bfb7-106">強烈建議客戶在服務層級為註冊機構和 Web 服務啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="8bfb7-107">如果已為全域層級的註冊機構和 Web 服務啟用被動式驗證，則對於不是使用具有累積更新的 Lync 2013 登入的使用者，這可能會導致組織範圍的驗證失敗：2013用戶端桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="8bfb7-108">Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="8bfb7-108">Web Service Configuration</span></span>

<span data-ttu-id="8bfb7-109">下列步驟說明如何針對 Director、Enterprise Pool 和 Standard Edition server 建立自訂 web 服務設定，以進行被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="8bfb7-110">**建立自訂 web 服務設定**</span><span class="sxs-lookup"><span data-stu-id="8bfb7-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="8bfb7-111">使用 Lync 系統管理員帳戶，以累計更新登入 Lync Server 2013： 7 2013 月前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="8bfb7-112">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="8bfb7-113">從 [Lync Server 管理命令介面] 命令列中，執行下列命令，為每個 Director、Enterprise 集區和 Standard Edition Server 建立新的 Web 服務設定，以進行被動式驗證：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="8bfb7-114">WsFedPassiveMetadataUri FQDN 的值為 AD FS 2.0 伺服器的同盟服務名稱。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="8bfb7-115">您可以在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下功能窗格中的 [ <STRONG>服務</STRONG> ]，然後選取 [ <STRONG>編輯同盟服務屬性</STRONG>]，即可找到 [同盟服務名稱] 值。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="8bfb7-116">執行下列命令，確認 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值已正確設定：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="8bfb7-117">若為用戶端，被動式驗證是 webticket 驗證的最低偏好驗證方法。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="8bfb7-118">針對將啟用被動驗證的所有 Director、Enterprise Pool 和 Standard Edition server，您必須執行下列命令來停用 Lync Web 服務中的所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="8bfb7-119">執行下列命令，確認已成功停用所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="8bfb7-120">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="8bfb7-120">Proxy Configuration</span></span>

<span data-ttu-id="8bfb7-121">停用 Lync Web 服務的憑證驗證時，Lync 用戶端會使用較不習慣的驗證類型，例如 Kerberos 或 NTLM，以驗證註冊機構服務。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="8bfb7-122">仍需要憑證驗證，讓 Lync 用戶端能夠取得 webticket，但必須停用註冊器服務的 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="8bfb7-123">下列步驟說明如何針對將啟用被動驗證的 Edge 集區、Enterprise 集區和 Standard Edition server 建立自訂 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="8bfb7-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="8bfb7-124">**建立自訂 proxy 設定**</span><span class="sxs-lookup"><span data-stu-id="8bfb7-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="8bfb7-125">從 [Lync Server 管理命令介面] 命令列中，為每個 Lync Server 2013 建立新的 proxy 設定，其累計更新為：7月 2013 Edge 集區、Enterprise Pool 和 Standard Edition Server，可執行下列命令來啟用被動驗證：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="8bfb7-126">執行下列命令，確認已成功停用所有其他 proxy 驗證類型：</span><span class="sxs-lookup"><span data-stu-id="8bfb7-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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


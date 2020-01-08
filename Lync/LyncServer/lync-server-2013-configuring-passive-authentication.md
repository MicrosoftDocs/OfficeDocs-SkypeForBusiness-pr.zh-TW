---
title: Lync Server 2013：設定被動式驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40975760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="b913a-102">設定 Lync Server 2013 被動式驗證</span><span class="sxs-lookup"><span data-stu-id="b913a-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b913a-103">_**主題上次修改日期：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="b913a-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="b913a-104">下列章節說明如何使用累積更新設定 Lync Server 2013：2013以支援被動驗證。</span><span class="sxs-lookup"><span data-stu-id="b913a-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="b913a-105">一旦啟用，即會要求啟用雙因素驗證的 Lync 使用者使用 [物理或虛擬智慧卡] 和有效的 PIN，以使用 Lync 2013，以累積更新的方式登入：2013用戶端年7月。</span><span class="sxs-lookup"><span data-stu-id="b913a-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b913a-106">強烈建議客戶針對服務層級的註冊機構和 Web 服務啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="b913a-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="b913a-107">如果針對全域層級的註冊機構和 Web 服務啟用被動式驗證，可能會導致無法使用 Lync 2013 以累積更新登入的使用者，從而導致組織範圍的驗證失敗：2013用戶端電腦用戶端。</span><span class="sxs-lookup"><span data-stu-id="b913a-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="b913a-108">Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b913a-108">Web Service Configuration</span></span>

<span data-ttu-id="b913a-109">下列步驟說明如何為控制器、企業版池和標準版伺服器（將為被動驗證啟用）建立自訂的 web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="b913a-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="b913a-110">**建立自訂的 web 服務設定**</span><span class="sxs-lookup"><span data-stu-id="b913a-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="b913a-111">以累積更新登入您的 Lync Server 2013：使用 Lync 系統管理員帳戶的2013前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b913a-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="b913a-112">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b913a-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="b913a-113">從 Lync Server Management Shell 命令列，為每個主管、企業版池及標準版伺服器建立新的 Web 服務設定，只要執行下列命令，即可啟用被動式驗證：</span><span class="sxs-lookup"><span data-stu-id="b913a-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="b913a-114">WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 伺服器的識別身分同盟服務名稱。</span><span class="sxs-lookup"><span data-stu-id="b913a-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="b913a-115">在 AD FS 2.0 管理主控台中，您可以在 [功能窗格] 中以滑鼠右鍵按一下 [<STRONG>服務</STRONG>]，然後選取 [<STRONG>編輯同盟服務屬性</STRONG>]，找到 [同盟服務名稱] 值。</span><span class="sxs-lookup"><span data-stu-id="b913a-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="b913a-116">執行下列命令，確認已正確設定 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：</span><span class="sxs-lookup"><span data-stu-id="b913a-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="b913a-117">針對用戶端，被動式驗證是 webticket 驗證的最不可取的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="b913a-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="b913a-118">針對將啟用被動式驗證的所有控制器、企業版池及標準版伺服器，您必須在 Lync Web 服務中執行下列命令停用所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="b913a-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="b913a-119">執行下列命令，確認所有其他驗證類型都已成功停用：</span><span class="sxs-lookup"><span data-stu-id="b913a-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="b913a-120">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="b913a-120">Proxy Configuration</span></span>

<span data-ttu-id="b913a-121">當您針對 Lync Web 服務停用認證驗證時，Lync 用戶端會使用較不可取的喜好驗證類型（例如 Kerberos 或 NTLM）來驗證註冊機構服務。</span><span class="sxs-lookup"><span data-stu-id="b913a-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="b913a-122">您仍需要證書驗證來允許 Lync 用戶端檢索 webticket，不過，必須針對註冊機構服務停用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="b913a-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="b913a-123">下列步驟說明如何針對要啟用被動式驗證的邊緣池、企業版池及標準版伺服器建立自訂 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="b913a-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="b913a-124">**建立自訂 proxy 配置**</span><span class="sxs-lookup"><span data-stu-id="b913a-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="b913a-125">從 Lync Server Management Shell 命令列，使用累積更新為每個 Lync Server 2013 建立新的 proxy 設定：年 7 2013 月的邊緣池、企業版池及標準版伺服器（可透過執行）啟用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b913a-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="b913a-126">執行下列命令，確認所有其他 proxy 驗證類型都已順利停用：</span><span class="sxs-lookup"><span data-stu-id="b913a-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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


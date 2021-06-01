---
title: 診斷商務用 Skype Online 連接器的連線問題
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 疑難排解如何建立遠端 PowerShell 會話以連線至 商務用 Skype Online，包括 Import-Module、並行 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: 02952ea878424cb0b5e84337051c30660101d144
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238894"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="ce760-103">診斷商務用 Skype Online 連接器的連線問題</span><span class="sxs-lookup"><span data-stu-id="ce760-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ce760-104">本主題提供可協助診斷及解決當您嘗試建立連線至線上的遠端 Microsoft PowerShell 會話時商務用 Skype的資訊。</span><span class="sxs-lookup"><span data-stu-id="ce760-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ce760-105">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="ce760-105">See the following sections:</span></span>
  
- [<span data-ttu-id="ce760-106">由於執行策略Windows PowerShell模組錯誤</span><span class="sxs-lookup"><span data-stu-id="ce760-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="ce760-107">錯誤版本錯誤導致輸入模組錯誤Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce760-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="ce760-108">當 WinRM 基本驗證已停用時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce760-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="ce760-109">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="ce760-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="ce760-110">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="ce760-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="ce760-111">使用者無法進行登錄</span><span class="sxs-lookup"><span data-stu-id="ce760-111">Sign in failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="ce760-112">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="ce760-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="ce760-113">連線至租使用者的能力已在 商務用 Skype Online 中停用</span><span class="sxs-lookup"><span data-stu-id="ce760-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="ce760-114">已超出此使用者在 商務用 Skype 命令的上限</span><span class="sxs-lookup"><span data-stu-id="ce760-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="ce760-115">超過此租使用者在 商務用 Skype 中並行命令命令數上限</span><span class="sxs-lookup"><span data-stu-id="ce760-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="ce760-116">根據預設，PowerShell 會話在六十分鐘後會結束。</span><span class="sxs-lookup"><span data-stu-id="ce760-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="ce760-117">若要重新連接，您必須關閉會話並啟動新的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ce760-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="ce760-118">新版 [商務用 Skype Online、Windows PowerShell 模組 (2046.123 - 已發佈 10/2/2019) 最近](https://www.microsoft.com/download/details.aspx?id=39366)推出，其中包含名為 **Enable-CsOnlineSessionForReconnection** 的新 Cmdlet，可減輕 60 分鐘的時空問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="ce760-119">PowerShell 會話會重新連接和驗證，以便重新使用，而不需要啟動新實例重新連接。</span><span class="sxs-lookup"><span data-stu-id="ce760-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="ce760-120">Import-Module執行Windows PowerShell錯誤</span><span class="sxs-lookup"><span data-stu-id="ce760-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="ce760-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="ce760-122">PowerShell 執行策略可協助判斷哪些組組檔案可以載入至 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。</span><span class="sxs-lookup"><span data-stu-id="ce760-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="ce760-123">除非執行策略設定為 RemoteSigned，否則至少無法商務用 Skype線上連接器模組。</span><span class="sxs-lookup"><span data-stu-id="ce760-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="ce760-124">如果沒有，則當您嘗試輸入模組時，會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="ce760-125">錯誤：Import-Module：檔案 C：無法載入程式檔案一般檔案<em>Microsoft Lync Server \\ \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1，因為系統已停用執行中的腳本。詳細資訊，請參閱在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="ce760-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="ce760-126">**解析度** 若要解決此問題，請以系統管理員角色啟動 PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ce760-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="ce760-127">有關執行策略的詳細資訊，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="ce760-127">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="ce760-128">Import-Module錯誤由不正確的版本Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce760-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="ce760-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="ce760-130">商務用 Skype線上連接器模組只能在 3.0 Windows PowerShell下執行。</span><span class="sxs-lookup"><span data-stu-id="ce760-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="ce760-131">如果您嘗試在先前版本的 PowerShell 下輸入模組，則導入程式將會失敗，而錯誤訊息與以下訊息類似：</span><span class="sxs-lookup"><span data-stu-id="ce760-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this message:</span></span>
  
  - <span data-ttu-id="ce760-132">\**錯誤\*\*\*：Import-Module：載入的 PowerShell 版本為 '2.0'。模組 'D：程式檔案共同檔案 \\ \\ Microsoft Lync Server \\ 2013 \\ 模組 \\ LyncOnlineConnector \\LyncOnlineConnector.psd1' 需要執行的最低 PowerShell 版本為 '3.0' 。請確認 PowerShell 的安裝，然後再試一次。*</span><span class="sxs-lookup"><span data-stu-id="ce760-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="ce760-133">**解決方法**：修正此問題的唯一方法，是安裝 3.0 Windows PowerShell 3.0，可從 Microsoft 下載中心在 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .</span><span class="sxs-lookup"><span data-stu-id="ce760-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="ce760-134">當 WinRM 基本驗證已停用時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce760-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="ce760-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="ce760-136">最新版本的 商務用 Skype Online Connector 模組使用新式驗證，但基礎 Windows 遠端系統管理 (WinRM) 用戶端必須配置為允許基本驗證。</span><span class="sxs-lookup"><span data-stu-id="ce760-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="ce760-137">新式驗證使用記名權杖，通常是在授權 *：Bearer 標頭中* 傳遞。</span><span class="sxs-lookup"><span data-stu-id="ce760-137">Modern authentication uses bearer tokens, which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="ce760-138">Windows PowerShell建立 PowerShell 商務用 Skype，不允許操作此頁標題。</span><span class="sxs-lookup"><span data-stu-id="ce760-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="ce760-139">PowerShell 商務用 Skype使用 *授權：基本* 頁首來傳遞承載權杖。</span><span class="sxs-lookup"><span data-stu-id="ce760-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="ce760-140">請參閱[下載並安裝Windows PowerShell，](./download-and-install-windows-powershell-5-1.md)以取得如何啟用 WinRM for Basic 驗證的指示。</span><span class="sxs-lookup"><span data-stu-id="ce760-140">See [Download and install Windows PowerShell](./download-and-install-windows-powershell-5-1.md) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="ce760-141">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="ce760-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="ce760-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-142"><a name="BKMKFailedConnect"> </a></span></span>

> [!WARNING] 
> <span data-ttu-id="ce760-143">商務用線上連接器已Skype ID 驗證。</span><span class="sxs-lookup"><span data-stu-id="ce760-143">Live ID authentication has been deprecated for Skype For Business online Connector.</span></span> <span data-ttu-id="ce760-144">使用 Teams PowerShell 模組來管理線上租使用者。</span><span class="sxs-lookup"><span data-stu-id="ce760-144">Use the Teams PowerShell Module to manage the online tenant.</span></span> <span data-ttu-id="ce760-145">管理混合式環境時，請升級至最新的累積更新或使用 oAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="ce760-145">When managing hybrid environments, upgrade to latest cumulative update or use oAuth authentication.</span></span>

<span data-ttu-id="ce760-146">您的連接嘗試失敗的原因通常有三種，原因如下：</span><span class="sxs-lookup"><span data-stu-id="ce760-146">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="ce760-147">\**錯誤\*\*\*：Get-CsWebTicket：無法連接即時識別碼伺服器。請確定 Proxy 已啟用，或電腦已與即時識別碼伺服器建立網路連接。*</span><span class="sxs-lookup"><span data-stu-id="ce760-147">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live ID servers.*</span></span>

- <span data-ttu-id="ce760-148">**解決** 方式：此錯誤通常表示 Microsoft Online Services 登入小幫手並未進行。</span><span class="sxs-lookup"><span data-stu-id="ce760-148">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="ce760-149">您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態：</span><span class="sxs-lookup"><span data-stu-id="ce760-149">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="ce760-150">如果服務未執行，請用此命令啟動服務：</span><span class="sxs-lookup"><span data-stu-id="ce760-150">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="ce760-151">如果服務執行中，您可能會遇到電腦與 Microsoft Live ID 驗證服務器之間的網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-151">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="ce760-152">若要檢查這項功能，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="ce760-152">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="ce760-153">請嘗試從Microsoft 365登Office 365或登陸。</span><span class="sxs-lookup"><span data-stu-id="ce760-153">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="ce760-154">如果失敗，您可能遇到網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-154">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="ce760-155">較不常見的是，可能是 Microsoft Live ID 驗證服務器的連接 URI 已配置為錯誤的值。</span><span class="sxs-lookup"><span data-stu-id="ce760-155">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="ce760-156">如果您已經判斷系統正在Sign-In小幫手，而且您沒有遇到網路連接問題，這可能是問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-156">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="ce760-157">在這種情況下，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="ce760-157">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="ce760-158">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="ce760-158">Failed to load Live ID module</span></span>
<span data-ttu-id="ce760-159"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-159"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="ce760-160">使用 PowerShell 管理線上版的先決條件之一商務用 Skype安裝 Microsoft Online 服務登錄小幫手。</span><span class="sxs-lookup"><span data-stu-id="ce760-160">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="ce760-161">如果未安裝登錄小幫手，當您嘗試使用線上帳戶建立遠端會話時，商務用 Skype訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-161">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="ce760-162">\**錯誤\*\*\*：Get-CsWebTicket：無法載入 Live ID 模組。確認已安裝正確版本的 Live Id 登錄小幫手。*</span><span class="sxs-lookup"><span data-stu-id="ce760-162">**Error**: *Get-CsWebTicket : Can't load Live ID module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="ce760-163">**解決** 方式：Microsoft Online Services 登入小幫手可在 Microsoft Online Services 的 Microsoft 下載中心Sign-In [IT 專業人員 RTW](https://www.microsoft.com/download/details.aspx?id=28177)小幫手</span><span class="sxs-lookup"><span data-stu-id="ce760-163">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="ce760-164">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="ce760-164">Logon failed for the user</span></span>
<span data-ttu-id="ce760-165"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-165"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="ce760-166">當您嘗試遠端連線至 商務用 Skype連線時，您必須提供線上使用者帳戶中有效商務用 Skype使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="ce760-166">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="ce760-167">如果沒有，登入會失敗，以及類似此訊息的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-167">If you do not, logon will fail along with an error message similar to this message:</span></span>

- <span data-ttu-id="ce760-168">\**錯誤\*\*\*：Get-CsWebTicket：登入失敗的使用者'kenmyer@litwareinc.com'。建立新的 PSCredential 物件，確定您所使用的使用者名稱和密碼正確無誤。*</span><span class="sxs-lookup"><span data-stu-id="ce760-168">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="ce760-169">**解決方法**：如果您認為您使用的是有效的使用者帳戶，而且您擁有正確的密碼，請再次嘗試登陸。</span><span class="sxs-lookup"><span data-stu-id="ce760-169">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="ce760-170">如果失敗，請使用相同的認證，並嘗試在 中登錄 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。</span><span class="sxs-lookup"><span data-stu-id="ce760-170">If that fails, use the same credentials and try to sign in at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="ce760-171">如果您無法在那裡登錄，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="ce760-171">If you're unable to sign in there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="ce760-172">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="ce760-172">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="ce760-173"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-173"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="ce760-174">除非您是租使用者系統管理員群組的成員，否則您無法與商務用Skype Online 進行遠端 PowerShell 連線。</span><span class="sxs-lookup"><span data-stu-id="ce760-174">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="ce760-175">如果沒有，您的連接嘗試將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-175">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="ce760-176">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：使用者 'user@foo.com' 沒有管理此租使用者的許可權 *。您可以將使用者指派給適當的 RBAC 角色，以授予許可權。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="ce760-176">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="ce760-177">**解決方法**：如果您認為自己是或應該是租使用者系統管理員群組的成員，您必須與 Microsoft 支援服務聯繫。</span><span class="sxs-lookup"><span data-stu-id="ce760-177">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="ce760-178">連線至租使用者的能力已在 商務用 Skype Online 中停用</span><span class="sxs-lookup"><span data-stu-id="ce760-178">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="ce760-179"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-179"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="ce760-180">若要使用 PowerShell 商務用 Skype Online，您租使用者 PowerShell 策略的 EnableRemotePowerShellAccess 屬性必須設為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="ce760-180">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="ce760-181">如果沒有，您的連接將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-181">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="ce760-182">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：已停用使用遠端 PowerShell 會話連接到此租使用者的能力 *。請聯絡 Lync 協助以檢查此租使用者的租使用者 Powershell 政策。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="ce760-182">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="ce760-183">**解決方法**：如果您看到此錯誤訊息，您必須與 Microsoft 支援服務聯繫，並啟用遠端 PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="ce760-183">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="ce760-184">已超出此使用者在 商務用 Skype 命令的上限</span><span class="sxs-lookup"><span data-stu-id="ce760-184">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="ce760-185"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-185"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="ce760-186">每個系統管理員最多可同時使用三個遠端連線商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="ce760-186">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="ce760-187">如果您有三個遠端 PowerShell 連接已啟動並執行，任何嘗試進行第四次同時連接都會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-187">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="ce760-188">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此使用者並行命令命令的上限。關閉現有的命令命令或提高此使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="ce760-188">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="ce760-189">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="ce760-189">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="ce760-190">當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止會話。</span><span class="sxs-lookup"><span data-stu-id="ce760-190">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="ce760-191">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-191">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="ce760-192">已超出此租使用者在 商務用 Skype 的並行命令命令數目上限</span><span class="sxs-lookup"><span data-stu-id="ce760-192">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="ce760-193"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="ce760-193"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="ce760-194">雖然每個系統管理員可以同時連線至 商務用 Skype Online 租使用者，但不允許單一租使用者同時連線超過 20 個。</span><span class="sxs-lookup"><span data-stu-id="ce760-194">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="ce760-195">例如，六個系統管理員可能各自有三個開啟的會話。</span><span class="sxs-lookup"><span data-stu-id="ce760-195">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="ce760-196">如果第四個系統管理員嘗試建立超過兩個 (導致總共 21 個同時) ，此嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ce760-196">If a fourth administrator tries to make more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="ce760-197">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此租使用者並行命令命令的上限。關閉現有的 shell 或提高此租使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="ce760-197">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message: The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="ce760-198">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="ce760-198">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="ce760-199">當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。</span><span class="sxs-lookup"><span data-stu-id="ce760-199">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="ce760-200">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="ce760-200">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="ce760-201">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce760-201">Related topics</span></span>
[<span data-ttu-id="ce760-202">使用電腦設定商務用 skype 線上管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce760-202">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

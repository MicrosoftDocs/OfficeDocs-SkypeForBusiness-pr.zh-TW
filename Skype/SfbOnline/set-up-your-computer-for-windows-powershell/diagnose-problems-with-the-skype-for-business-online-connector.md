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
description: 疑難排解如何建立遠端 PowerShell 會話以連線至商務用 Skype Online，包括 Import-Module、並行 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: 6edaa33244a3192f83289020fe12051ab5f9fb6b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097249"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="f4d70-103">診斷商務用 Skype Online 連接器的連線問題</span><span class="sxs-lookup"><span data-stu-id="f4d70-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="f4d70-104">本主題提供可協助診斷及解決當您嘗試建立連線至商務用 Skype Online 的遠端 Microsoft PowerShell 會話時可能會發生的問題的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4d70-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="f4d70-105">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="f4d70-105">See the following sections:</span></span>
  
- [<span data-ttu-id="f4d70-106">Windows PowerShell 執行策略所導致之 Import-Module 錯誤</span><span class="sxs-lookup"><span data-stu-id="f4d70-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="f4d70-107">Windows PowerShell 版本不正確所造成的 Import-Module 錯誤</span><span class="sxs-lookup"><span data-stu-id="f4d70-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="f4d70-108">當 WinRM 基本驗證已停用時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="f4d70-109">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="f4d70-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="f4d70-110">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="f4d70-111">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-111">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="f4d70-112">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="f4d70-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="f4d70-113">商務用 Skype Online 已停用連線至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="f4d70-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="f4d70-114">已超過商務用 Skype Online 中此使用者的並行命令命令數目上限</span><span class="sxs-lookup"><span data-stu-id="f4d70-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="f4d70-115">已超出商務用 Skype Online 中此租使用者並行命令的上限</span><span class="sxs-lookup"><span data-stu-id="f4d70-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="f4d70-116">根據預設，PowerShell 會話在六十分鐘後會結束。</span><span class="sxs-lookup"><span data-stu-id="f4d70-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="f4d70-117">若要重新連接，您必須關閉會話並啟動新的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="f4d70-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="f4d70-118">新版商務用 Skype [Online、Windows PowerShell 模組 (2046.123 - 已發佈 10/2/2019) 最近](https://www.microsoft.com/download/details.aspx?id=39366)推出，其中包含名為 **Enable-CsOnlineSessionForReconnection** 的新 Cmdlet，可減輕 60 分鐘的時空問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="f4d70-119">PowerShell 會話會重新連接和驗證，以便重新使用，而不需要啟動新實例重新連接。</span><span class="sxs-lookup"><span data-stu-id="f4d70-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="f4d70-120">Import-Module PowerShell 執行策略所造成的錯誤</span><span class="sxs-lookup"><span data-stu-id="f4d70-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="f4d70-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="f4d70-122">PowerShell 執行策略可協助判斷哪些組組檔案可以載入至 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。</span><span class="sxs-lookup"><span data-stu-id="f4d70-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="f4d70-123">除非執行策略設定為 RemoteSigned，否則至少無法導入商務用 Skype Online Connector 模組。</span><span class="sxs-lookup"><span data-stu-id="f4d70-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="f4d70-124">如果沒有，則當您嘗試輸入模組時，會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="f4d70-125">錯誤：Import-Module：檔案 C：無法載入程式檔案一般檔案<em>Microsoft Lync Server \\ \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1，因為系統已停用執行中的腳本。詳細資訊，請參閱在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="f4d70-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="f4d70-126">**解析度** 若要解決此問題，請以系統管理員角色啟動 PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f4d70-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="f4d70-127">有關執行策略的詳細資訊，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="f4d70-127">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="f4d70-128">Import-Module Windows PowerShell 版本不正確所造成的錯誤</span><span class="sxs-lookup"><span data-stu-id="f4d70-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="f4d70-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="f4d70-130">商務用 Skype Online 連接器模組只能在 Windows PowerShell 3.0 下執行。</span><span class="sxs-lookup"><span data-stu-id="f4d70-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="f4d70-131">如果您嘗試在先前版本的 PowerShell 下輸入模組，則導入程式將會失敗，出現錯誤訊息，類似這樣：</span><span class="sxs-lookup"><span data-stu-id="f4d70-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="f4d70-132">\**錯誤\*\*\*：Import-Module：載入的 PowerShell 版本為 '2.0'。模組 'D：程式檔案一般 \\ 檔案 Microsoft Lync Server \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\LyncOnlineConnector.psd1' 需要執行的最低 PowerShell 版本為 '3.0' 。請確認 PowerShell 的安裝，然後再試一次。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="f4d70-133">**解決** 方式：修正此問題的唯一方法，就是安裝 Windows PowerShell 3.0，可從 Microsoft 下載中心于 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .</span><span class="sxs-lookup"><span data-stu-id="f4d70-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="f4d70-134">當 WinRM 基本驗證已停用時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="f4d70-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="f4d70-136">最新版的商務用 Skype Online Connector 模組使用新式驗證，但基礎 Windows 遠端系統管理 (WinRM) 用戶端必須配置為允許基本驗證。</span><span class="sxs-lookup"><span data-stu-id="f4d70-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="f4d70-137">新式驗證會使用記名權杖，這些權杖通常會在授權 *：Bearer 標頭中* 傳遞。</span><span class="sxs-lookup"><span data-stu-id="f4d70-137">Modern authentication uses bearer tokens which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="f4d70-138">建立商務用 Skype PowerShell 的 Windows PowerShell 不允許操作此頁標題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="f4d70-139">相反地，商務用 Skype PowerShell 會使用 *授權：基本* 頁首來傳遞記名權杖。</span><span class="sxs-lookup"><span data-stu-id="f4d70-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="f4d70-140">請參閱 [下載並安裝 Windows PowerShell，](./download-and-install-windows-powershell-5-1.md) 以取得如何啟用 WinRM 基本驗證的指示。</span><span class="sxs-lookup"><span data-stu-id="f4d70-140">See [Download and install Windows PowerShell](./download-and-install-windows-powershell-5-1.md) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="f4d70-141">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="f4d70-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="f4d70-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-142"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="f4d70-143">您的連接嘗試失敗的原因通常有三種，原因如下：</span><span class="sxs-lookup"><span data-stu-id="f4d70-143">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="f4d70-144">\**錯誤\*\*\*：Get-CsWebTicket：無法連接即時識別碼伺服器。請確定 Proxy 已啟用，或電腦已與即時識別碼伺服器建立網路連接。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-144">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="f4d70-145">**解決** 方式：此錯誤通常表示 Microsoft Online Services 登入小幫手並未進行。</span><span class="sxs-lookup"><span data-stu-id="f4d70-145">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="f4d70-146">您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態：</span><span class="sxs-lookup"><span data-stu-id="f4d70-146">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="f4d70-147">如果服務未執行，請用此命令啟動服務：</span><span class="sxs-lookup"><span data-stu-id="f4d70-147">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="f4d70-148">如果服務執行中，您可能會遇到電腦與 Microsoft Live ID 驗證服務器之間的網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-148">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="f4d70-149">若要檢查這項功能，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="f4d70-149">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="f4d70-150">請嘗試從這裡登陸 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f4d70-150">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="f4d70-151">如果失敗，您可能遇到網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-151">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="f4d70-152">較不常見的是，可能是 Microsoft Live ID 驗證服務器的連接 URI 已配置為錯誤的值。</span><span class="sxs-lookup"><span data-stu-id="f4d70-152">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="f4d70-153">如果您已經判斷系統正在Sign-In小幫手，而且您沒有遇到網路連接問題，這可能是問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-153">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="f4d70-154">在這種情況下，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="f4d70-154">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="f4d70-155">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-155">Failed to load Live ID module</span></span>
<span data-ttu-id="f4d70-156"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-156"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="f4d70-157">使用 PowerShell 管理商務用 Skype Online 的先決條件之一是安裝 Microsoft Online 服務登錄小幫手。</span><span class="sxs-lookup"><span data-stu-id="f4d70-157">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="f4d70-158">如果未安裝登錄小幫手，當您嘗試使用商務用 Skype Online 建立遠端會話時，會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-158">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="f4d70-159">\**錯誤\*\*\*：Get-CsWebTicket：無法載入 Live Id 模組。確認已安裝正確版本的 Live Id 登錄小幫手。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-159">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="f4d70-160">**解決** 方式：Microsoft Online Services 登入小幫手可在 Microsoft Online Services 的 Microsoft 下載中心Sign-In [IT 專業人員 RTW](https://www.microsoft.com/download/details.aspx?id=28177)小幫手</span><span class="sxs-lookup"><span data-stu-id="f4d70-160">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="f4d70-161">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="f4d70-161">Logon failed for the user</span></span>
<span data-ttu-id="f4d70-162"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-162"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="f4d70-163">當您嘗試進行遠端連線至商務用 Skype Online 時，必須提供有效的商務用 Skype Online 使用者帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="f4d70-163">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="f4d70-164">如果沒有，登入將會失敗，以及類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-164">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="f4d70-165">\**錯誤\*\*\*：Get-CsWebTicket：登入失敗的使用者'kenmyer@litwareinc.com'。請建立新的 PSCredential 物件，確認您所使用的使用者名稱和密碼正確無誤。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-165">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="f4d70-166">**解決方法**：如果您認為您使用的是有效的使用者帳戶，而且您擁有正確的密碼，請再次嘗試登陸。</span><span class="sxs-lookup"><span data-stu-id="f4d70-166">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="f4d70-167">如果失敗，請使用相同的認證，並嘗試登入 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。</span><span class="sxs-lookup"><span data-stu-id="f4d70-167">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="f4d70-168">如果您無法登入，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="f4d70-168">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="f4d70-169">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="f4d70-169">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="f4d70-170"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-170"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="f4d70-171">除非您是租使用者系統管理員群組的成員，否則您無法與商務用Skype Online 進行遠端 PowerShell 連線。</span><span class="sxs-lookup"><span data-stu-id="f4d70-171">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="f4d70-172">如果沒有，您的連接嘗試將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-172">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="f4d70-173">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：使用者 'user@foo.com' 沒有管理此租使用者的許可權 *。您可以將使用者指派給適當的 RBAC 角色，以授予許可權。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-173">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="f4d70-174">**解決方法**：如果您認為自己是或應該是租使用者系統管理員群組的成員，您必須與 Microsoft 支援服務聯繫。</span><span class="sxs-lookup"><span data-stu-id="f4d70-174">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="f4d70-175">商務用 Skype Online 已停用連線至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="f4d70-175">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="f4d70-176"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-176"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="f4d70-177">若要使用 PowerShell 管理商務用 Skype Online，您租使用者 PowerShell 策略的 EnableRemotePowerShellAccess 屬性必須設為  `True` 。</span><span class="sxs-lookup"><span data-stu-id="f4d70-177">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="f4d70-178">如果沒有，您的連接將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-178">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="f4d70-179">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：已停用使用遠端 PowerShell 會話連接到此租使用者的能力 *。請聯絡 Lync Help 以檢查此租使用者的租使用者 Powershell 政策。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="f4d70-179">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="f4d70-180">**解決方法**：如果您看到此錯誤訊息，您必須與 Microsoft 支援服務聯繫，並啟用遠端 PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="f4d70-180">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="f4d70-181">已超過商務用 Skype Online 中此使用者的並行命令命令數目上限</span><span class="sxs-lookup"><span data-stu-id="f4d70-181">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="f4d70-182"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-182"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="f4d70-183">每位系統管理員最多可同時使用三個遠端連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="f4d70-183">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="f4d70-184">如果您有三個遠端 PowerShell 連接已啟動並執行，任何嘗試進行第四次同時連接都會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-184">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="f4d70-185">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此使用者並行命令命令的上限。關閉現有的命令命令或提高此使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="f4d70-185">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="f4d70-186">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="f4d70-186">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="f4d70-187">完成商務用 Skype Online 會話後，建議您使用 **Remove-PSSession** Cmdlet 來終止會話。</span><span class="sxs-lookup"><span data-stu-id="f4d70-187">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="f4d70-188">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-188">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="f4d70-189">已超出商務用 Skype Online 中此租使用者並行命令的上限</span><span class="sxs-lookup"><span data-stu-id="f4d70-189">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="f4d70-190"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d70-190"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="f4d70-191">雖然每個系統管理員可同時與商務用 Skype Online 租使用者建立三個連線，但不允許單一租使用者同時連線超過 20 個。</span><span class="sxs-lookup"><span data-stu-id="f4d70-191">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="f4d70-192">例如，六個系統管理員可能各自有三個開啟的會話。</span><span class="sxs-lookup"><span data-stu-id="f4d70-192">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="f4d70-193">如果第四個系統管理員嘗試建立超過 2 個 (，導致總共 21 個同時) ，此嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f4d70-193">If a fourth administrator tries to make more than 2 connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="f4d70-194">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此租使用者並行命令命令的上限。關閉現有的 shell 或提高此租使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="f4d70-194">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="f4d70-195">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="f4d70-195">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="f4d70-196">完成商務用 Skype Online 會話後，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。</span><span class="sxs-lookup"><span data-stu-id="f4d70-196">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="f4d70-197">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="f4d70-197">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="f4d70-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="f4d70-198">Related topics</span></span>
[<span data-ttu-id="f4d70-199">使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦</span><span class="sxs-lookup"><span data-stu-id="f4d70-199">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

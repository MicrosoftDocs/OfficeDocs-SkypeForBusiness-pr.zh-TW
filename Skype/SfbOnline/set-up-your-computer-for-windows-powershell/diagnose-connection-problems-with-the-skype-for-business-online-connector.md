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
ms.openlocfilehash: f4bcb9c758d1660cafd7a6bd3f57c95d6bf3b546
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238904"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="20599-103">診斷商務用 Skype Online 連接器的連線問題</span><span class="sxs-lookup"><span data-stu-id="20599-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="20599-104">本主題提供可協助診斷及解決當您嘗試建立連線至線上的遠端 Microsoft PowerShell 會話時商務用 Skype的資訊。</span><span class="sxs-lookup"><span data-stu-id="20599-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="20599-105">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="20599-105">See the following sections:</span></span>
  
- [<span data-ttu-id="20599-106">由於執行策略Windows PowerShell模組錯誤</span><span class="sxs-lookup"><span data-stu-id="20599-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="20599-107">錯誤版本錯誤導致輸入模組錯誤Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20599-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="20599-108">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="20599-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="20599-109">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="20599-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="20599-110">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="20599-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="20599-111">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="20599-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="20599-112">連線至租使用者的能力已在 商務用 Skype Online 中停用</span><span class="sxs-lookup"><span data-stu-id="20599-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [<span data-ttu-id="20599-113">已超出此使用者在 商務用 Skype 命令的上限</span><span class="sxs-lookup"><span data-stu-id="20599-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="20599-114">已超出此租使用者在 商務用 Skype 的並行命令命令數目上限</span><span class="sxs-lookup"><span data-stu-id="20599-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="20599-115">Import-Module執行Windows PowerShell錯誤</span><span class="sxs-lookup"><span data-stu-id="20599-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="20599-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="20599-117">PowerShell 執行策略可協助判斷哪些組組檔案可以載入至 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。</span><span class="sxs-lookup"><span data-stu-id="20599-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="20599-118">除非執行策略設定為 RemoteSigned，否則至少無法商務用 Skype線上連接器模組。</span><span class="sxs-lookup"><span data-stu-id="20599-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="20599-119">如果沒有，則當您嘗試輸入模組時，會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="20599-120">錯誤：Import-Module：檔案 C：無法載入程式檔案一般檔案<em>Microsoft Lync Server \\ \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1，因為系統已停用執行中的腳本。詳細資訊，請參閱在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="20599-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="20599-121">**解決方法**：若要解決此問題，請以系統管理員的名次啟動 PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="20599-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="20599-122">有關執行策略的詳細資訊，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="20599-122">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="20599-123">Import-Module錯誤由不正確的版本Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20599-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="20599-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-124"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="20599-125">商務用 Skype線上連接器模組只能在 3.0 Windows PowerShell下執行。</span><span class="sxs-lookup"><span data-stu-id="20599-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="20599-126">如果您嘗試在先前版本的 PowerShell 下輸入模組，則導入程式將會失敗，並出現類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="20599-127">\**錯誤\*\*\*：Import-Module：載入的 PowerShell 版本為 '2.0'。模組 'D：程式檔案一般 \\ 檔案 Microsoft Lync Server \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\LyncOnlineConnector.psd1' 需要執行的最低 PowerShell 版本為 '3.0' 。請確認 PowerShell 的安裝，然後再試一次。*</span><span class="sxs-lookup"><span data-stu-id="20599-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="20599-128">**解決方法**：修正此問題的唯一方法，是安裝 3.0 Windows PowerShell 3.0，可從 Microsoft 下載中心在 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .</span><span class="sxs-lookup"><span data-stu-id="20599-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="20599-129">無法連接到 Live ID Server</span><span class="sxs-lookup"><span data-stu-id="20599-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="20599-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-130"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="20599-131">您的連接嘗試失敗的原因通常有三種，原因如下：</span><span class="sxs-lookup"><span data-stu-id="20599-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="20599-132">\**錯誤\*\*\*：Get-CsWebTicket：無法連接即時識別碼伺服器。請確定 Proxy 已啟用，或電腦已與即時識別碼伺服器建立網路連接。*</span><span class="sxs-lookup"><span data-stu-id="20599-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="20599-133">**解決** 方式：此錯誤通常表示 Microsoft Online Services 登入小幫手並未進行。</span><span class="sxs-lookup"><span data-stu-id="20599-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="20599-134">您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態：</span><span class="sxs-lookup"><span data-stu-id="20599-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="20599-135">如果服務未執行，請用此命令啟動服務：</span><span class="sxs-lookup"><span data-stu-id="20599-135">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="20599-136">如果服務執行中，您可能會遇到電腦與 Microsoft Live ID 驗證服務器之間的網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="20599-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="20599-137">若要檢查這項功能，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="20599-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="20599-138">請嘗試從Microsoft 365登Office 365或登陸。</span><span class="sxs-lookup"><span data-stu-id="20599-138">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="20599-139">如果失敗，您可能遇到網路連接問題。</span><span class="sxs-lookup"><span data-stu-id="20599-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="20599-140">較不常見的是，可能是 Microsoft Live ID 驗證服務器的連接 URI 已配置為錯誤的值。</span><span class="sxs-lookup"><span data-stu-id="20599-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="20599-141">如果您已經判斷系統正在Sign-In小幫手，而且您沒有遇到網路連接問題，這可能是問題。</span><span class="sxs-lookup"><span data-stu-id="20599-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="20599-142">在這種情況下，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="20599-142">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="20599-143">載入 Live ID 模組失敗</span><span class="sxs-lookup"><span data-stu-id="20599-143">Failed to load Live ID module</span></span>
<span data-ttu-id="20599-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-144"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="20599-145">使用 PowerShell 管理線上版的先決條件之一商務用 Skype安裝 Microsoft Online 服務登錄小幫手。</span><span class="sxs-lookup"><span data-stu-id="20599-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="20599-146">如果未安裝登錄小幫手，當您嘗試使用線上帳戶建立遠端會話時，商務用 Skype訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="20599-147">\**錯誤\*\*\*：Get-CsWebTicket：無法載入 Live Id 模組。確認已安裝正確版本的 Live Id 登錄小幫手。*</span><span class="sxs-lookup"><span data-stu-id="20599-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="20599-148">**解決** 方式：Microsoft Online Services 登入小幫手可在 Microsoft Online Services 的 Microsoft 下載中心Sign-In [IT 專業人員 RTW](https://www.microsoft.com/download/details.aspx?id=28177)小幫手</span><span class="sxs-lookup"><span data-stu-id="20599-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="20599-149">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="20599-149">Logon failed for the user</span></span>
<span data-ttu-id="20599-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-150"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="20599-151">當您嘗試進行遠端連線至線上商務用 Skype，您必須提供線上使用者帳戶中有效商務用 Skype使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="20599-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="20599-152">如果沒有，登入會失敗，以及類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="20599-153">\**錯誤\*\*\*：Get-CsWebTicket：登入失敗的使用者'kenmyer@litwareinc.com'。請建立新的 PSCredential 物件，確認您所使用的使用者名稱和密碼正確無誤。*</span><span class="sxs-lookup"><span data-stu-id="20599-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="20599-154">**解決方法**：如果您認為您使用的是有效的使用者帳戶，而且您擁有正確的密碼，請再次嘗試登陸。</span><span class="sxs-lookup"><span data-stu-id="20599-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="20599-155">如果失敗，請使用相同的認證，並嘗試登入 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。</span><span class="sxs-lookup"><span data-stu-id="20599-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="20599-156">如果您無法登入，請聯絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="20599-156">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="20599-157">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="20599-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="20599-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-158"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="20599-159">除非您是租使用者系統管理員群組的成員，否則您無法與商務用Skype Online 進行遠端 PowerShell 連線。</span><span class="sxs-lookup"><span data-stu-id="20599-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="20599-160">如果沒有，您的連接嘗試將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="20599-161">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：使用者 'user@foo.com' 沒有管理此租使用者的許可權 *。您可以將使用者指派給適當的 RBAC 角色，以授予許可權。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="20599-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="20599-162">**解決方法**：如果您認為自己是或應該是租使用者系統管理員群組的成員，您必須與 Microsoft 支援服務聯繫。</span><span class="sxs-lookup"><span data-stu-id="20599-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="20599-163">連線至租使用者的能力已在 商務用 Skype Online 中停用</span><span class="sxs-lookup"><span data-stu-id="20599-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="20599-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-164"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="20599-165">若要使用 PowerShell 商務用 Skype Online，您租使用者 PowerShell 策略的 EnableRemotePowerShellAccess 屬性必須設為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="20599-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="20599-166">如果沒有，您的連接將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="20599-167">錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：已停用使用遠端 PowerShell 會話連接到此租使用者的能力 *。請聯絡 Lync Help 以檢查此租使用者的租使用者 Powershell 政策。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="20599-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="20599-168">**解決方法**：如果您看到此錯誤訊息，您必須與 Microsoft 支援服務聯繫，並啟用遠端 PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="20599-168">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="20599-169">已超出此使用者在 商務用 Skype 命令的上限</span><span class="sxs-lookup"><span data-stu-id="20599-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="20599-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-170"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="20599-171">每個系統管理員最多可同時使用三個遠端連線商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="20599-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="20599-172">如果您有三個遠端 PowerShell 連接已啟動並執行，任何嘗試進行第四次同時連接都會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="20599-173">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此使用者並行命令命令的上限。關閉現有的 shell 或提高此使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="20599-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="20599-174">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="20599-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="20599-175">當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止會話。</span><span class="sxs-lookup"><span data-stu-id="20599-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="20599-176">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="20599-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="20599-177">超過此租使用者在 商務用 Skype 中並行命令命令數上限</span><span class="sxs-lookup"><span data-stu-id="20599-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="20599-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="20599-178"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="20599-179">雖然每個系統管理員可以同時連線至 商務用 Skype Online 租使用者，但不允許單一租使用者同時連線超過 20 個。</span><span class="sxs-lookup"><span data-stu-id="20599-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than twenty simultaneous connections.</span></span> <span data-ttu-id="20599-180">例如，六個系統管理員可能各自有三個開啟的會話。</span><span class="sxs-lookup"><span data-stu-id="20599-180">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="20599-181">如果第七個系統管理員嘗試開啟超過兩個 (導致總共 21 個同時) ，此嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="20599-181">If a seventh administrator tries to open more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="20599-182">\**錯誤\*\*\*：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此租使用者並行命令命令的上限。關閉現有的 shell 或提高此租使用者的配額。詳細資訊請參閱 [遠端疑難排解] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="20599-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="20599-183">**解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。</span><span class="sxs-lookup"><span data-stu-id="20599-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="20599-184">當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。</span><span class="sxs-lookup"><span data-stu-id="20599-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="20599-185">這可協助避免此問題。</span><span class="sxs-lookup"><span data-stu-id="20599-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="20599-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="20599-186">Related topics</span></span>
[<span data-ttu-id="20599-187">使用電腦設定商務用 skype 線上管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20599-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

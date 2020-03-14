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
description: 疑難排解建立用來連線到商務用 Skype Online 的遠端 PowerShell 會話，包括匯入模組、併發 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: be3500ea5573dab6daa3d8ff72a8de4f60566ee2
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637130"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="9aab5-103">診斷商務用 Skype Online 連接器的連線問題</span><span class="sxs-lookup"><span data-stu-id="9aab5-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="9aab5-104">本主題提供的資訊可協助您診斷並解決當您嘗試建立連線到商務用 Skype Online 的遠端 Microsoft PowerShell 會話時，可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="9aab5-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9aab5-105">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="9aab5-105">See the following sections:</span></span>
  
- [<span data-ttu-id="9aab5-106">Import-Windows PowerShell 執行原則所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="9aab5-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="9aab5-107">匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="9aab5-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- <span data-ttu-id="9aab5-108">[無法連線至 [Live ID] 伺服器](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)</span><span class="sxs-lookup"><span data-stu-id="9aab5-108">[Failed to connect to Live ID Server](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)</span></span>
    
- <span data-ttu-id="9aab5-109">[無法載入 [實際 ID] 模組](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)</span><span class="sxs-lookup"><span data-stu-id="9aab5-109">[Failed to load Live ID module](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)</span></span>
    
- [<span data-ttu-id="9aab5-110">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="9aab5-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="9aab5-111">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="9aab5-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="9aab5-112">在商務用 Skype Online 中已停用連接至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="9aab5-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [<span data-ttu-id="9aab5-113">已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限</span><span class="sxs-lookup"><span data-stu-id="9aab5-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="9aab5-114">已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限</span><span class="sxs-lookup"><span data-stu-id="9aab5-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="9aab5-115">Import-Windows PowerShell 執行原則所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="9aab5-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="9aab5-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="9aab5-117">PowerShell 執行原則可協助判斷哪些設定檔可以載入到 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。</span><span class="sxs-lookup"><span data-stu-id="9aab5-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="9aab5-118">除非執行原則已設定為 RemoteSigned，否則在最低限度的情況下，無法匯入商務用 Skype Online 連接器模組。</span><span class="sxs-lookup"><span data-stu-id="9aab5-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="9aab5-119">如果沒有，當您嘗試匯入模組時，您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="9aab5-120">**錯誤**：<em>匯入-模組：檔案 C\\： Program\\files 常見\\檔案 Microsoft Lync Server\\2013\\模組\\LyncOnlineConnector 無法載入 psm1，因為在這個系統上已停用執行腳本。如需詳細資訊，請參閱https://go.microsoft.com/fwlink/?LinkID=135170about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="9aab5-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="9aab5-121">**解決**方式：若要解決此問題，請以系統管理員的身分啟動 PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9aab5-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="9aab5-122">如需有關執行原則的詳細資訊，請參閱[關於執行](https://go.microsoft.com/fwlink/?LinkID=135170)原則。</span><span class="sxs-lookup"><span data-stu-id="9aab5-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="9aab5-123">匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="9aab5-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="9aab5-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-124"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="9aab5-125">商務用 Skype Online 連接器模組只能在 Windows PowerShell 3.0 下執行。</span><span class="sxs-lookup"><span data-stu-id="9aab5-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="9aab5-126">如果您嘗試在舊版 PowerShell 中匯入模組，匯入程式將會失敗，並顯示類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="9aab5-127">**錯誤**：匯*入-模組：載入的 PowerShell 版本是 "2.0"。Module to\\： Program files\\常見檔案\\Microsoft Lync Server 2013\\模組\\LyncOnlineConnector\\LyncOnlineConnector，psd1 ' 需要最小3.0 的 PowerShell 版本才能執行。請確認已安裝 PowerShell，然後再試一次。*</span><span class="sxs-lookup"><span data-stu-id="9aab5-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="9aab5-128">**解決**方式：修正這個問題的唯一方法是安裝 Windows PowerShell 3.0，此版本可從 Microsoft 下載中心取得[https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)。</span><span class="sxs-lookup"><span data-stu-id="9aab5-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="9aab5-129">無法連線至 [Live ID] 伺服器</span><span class="sxs-lookup"><span data-stu-id="9aab5-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="9aab5-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-130"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="9aab5-131">使用下列錯誤訊息時，連接嘗試可能會失敗的原因有三種：</span><span class="sxs-lookup"><span data-stu-id="9aab5-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="9aab5-132">**錯誤**： *CsWebTicket：無法連接即時 id 伺服器。請確定已啟用 proxy，或電腦有連線至 live id 伺服器的網路連線。*</span><span class="sxs-lookup"><span data-stu-id="9aab5-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="9aab5-133">**解決**方式：此錯誤通常表示 Microsoft Online Services 登入小幫手未執行。</span><span class="sxs-lookup"><span data-stu-id="9aab5-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="9aab5-134">您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態：</span><span class="sxs-lookup"><span data-stu-id="9aab5-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="9aab5-135">如果服務未執行，請使用此命令啟動服務：</span><span class="sxs-lookup"><span data-stu-id="9aab5-135">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="9aab5-136">如果服務正在執行，您可能會遇到您的電腦與 Microsoft Live ID 驗證服務器之間的網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="9aab5-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="9aab5-137">若要檢查此情況，請開啟 Internet Explorer，然後流覽至[ https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="9aab5-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="9aab5-138">嘗試從該處登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9aab5-138">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="9aab5-139">如果這種情況失敗，可能是遇到網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="9aab5-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="9aab5-140">不太常見，Microsoft Live ID 驗證服務器的連線 URI 可能已設定為錯誤的值。</span><span class="sxs-lookup"><span data-stu-id="9aab5-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="9aab5-141">如果您已確定登入小幫手正在執行，而且您沒有網路連線問題，這可能是問題所在。</span><span class="sxs-lookup"><span data-stu-id="9aab5-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="9aab5-142">在這種情況下，請與 Office 365 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="9aab5-142">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="9aab5-143">無法載入 [實際 ID] 模組</span><span class="sxs-lookup"><span data-stu-id="9aab5-143">Failed to load Live ID module</span></span>
<span data-ttu-id="9aab5-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-144"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="9aab5-145">使用 PowerShell 來管理商務用 Skype Online 的其中一個先決條件是安裝 Microsoft Online Services 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="9aab5-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="9aab5-146">如果未安裝登入小幫手，當您嘗試與商務用 Skype Online 建立遠端會話時，您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="9aab5-147">**錯誤**： *CsWebTicket：無法載入 [即時 Id] 模組。請確定已安裝 [正確版本的 Live Id 登入*小幫手]。</span><span class="sxs-lookup"><span data-stu-id="9aab5-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="9aab5-148">**解析度**：適用于[IT 專業人員的 microsoft Online services 登入](https://www.microsoft.com/download/details.aspx?id=28177)小幫手，Microsoft 下載中心提供 microsoft online services 登入小幫手 RTW</span><span class="sxs-lookup"><span data-stu-id="9aab5-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="9aab5-149">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="9aab5-149">Logon failed for the user</span></span>
<span data-ttu-id="9aab5-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-150"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="9aab5-151">當您嘗試建立與商務用 Skype Online 的遠端連線時，您必須提供有效的商務用 Skype Online 使用者帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="9aab5-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="9aab5-152">如果您沒有這樣做，登入將會失敗，並會出現類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="9aab5-153">**錯誤**： *CsWebTicket：使用者 ' kenmyer@litwareinc.com ' 登入失敗。請建立新的 PSCredential 物件，並確認您使用的是正確的使用者名稱和密碼。*</span><span class="sxs-lookup"><span data-stu-id="9aab5-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="9aab5-154">**解決方案**：如果您認為您使用的是有效的使用者帳戶，且您有正確的密碼，請嘗試再次登入。</span><span class="sxs-lookup"><span data-stu-id="9aab5-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="9aab5-155">如果失敗，請使用相同的認證，然後嘗試登入[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。</span><span class="sxs-lookup"><span data-stu-id="9aab5-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="9aab5-156">如果您無法登入，請與 Office 365 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="9aab5-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="9aab5-157">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="9aab5-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="9aab5-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-158"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="9aab5-159">除非您是租使用者管理員群組的成員，否則您無法建立商務用的遠端 PowerShell 連線 toSkype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="9aab5-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="9aab5-160">如果您不是這樣，您的連線嘗試將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="9aab5-161">**錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用者 ' user@foo.com」沒有管理此租使用者的許可權。您可以將使用者指派給適當的 RBAC 角色，以授與許可權。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="9aab5-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="9aab5-162">**解決**方式：如果您認為您是（或應該是租使用者管理員群組的成員），您必須與 Office 365 支援人員取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="9aab5-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="9aab5-163">在商務用 Skype Online 中已停用連接至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="9aab5-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="9aab5-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-164"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="9aab5-165">若要使用 PowerShell 來管理商務用 Skype Online，您必須將租使用者 PowerShell 原則的 EnableRemotePowerShellAccess 屬性設定`True`為。</span><span class="sxs-lookup"><span data-stu-id="9aab5-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="9aab5-166">如果不是，您的連線將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="9aab5-167">**錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用遠端 PowerShell 會話連線到此租使用者的功能已停用。請聯絡 Lync 說明，以查看此租使用者的租使用者 Powershell 原則。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="9aab5-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="9aab5-168">**解決**方式：如果您看到這則錯誤訊息，您必須與 Office 365 支援人員取得聯繫，並啟用遠端 PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="9aab5-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="9aab5-169">已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限</span><span class="sxs-lookup"><span data-stu-id="9aab5-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="9aab5-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-170"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="9aab5-171">每個系統管理員都允許最多三個同時遠端連線到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="9aab5-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="9aab5-172">如果您有三個遠端 PowerShell 連線且正在執行，則嘗試讓第四個同步連接的嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="9aab5-173">**錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此使用者的併發 shell 數目上限。關閉現有的程式外殼程式，或升高此使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*</span><span class="sxs-lookup"><span data-stu-id="9aab5-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="9aab5-174">**解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。</span><span class="sxs-lookup"><span data-stu-id="9aab5-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="9aab5-175">當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止會話。</span><span class="sxs-lookup"><span data-stu-id="9aab5-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="9aab5-176">這將協助您避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="9aab5-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="9aab5-177">已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限</span><span class="sxs-lookup"><span data-stu-id="9aab5-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="9aab5-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="9aab5-178"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="9aab5-179">雖然每個系統管理員都可以有多達三個同時連線到商務用 Skype Online 租使用者，但不允許單一租使用者有超過二十個的同時連接。</span><span class="sxs-lookup"><span data-stu-id="9aab5-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than twenty simultaneous connections.</span></span> <span data-ttu-id="9aab5-180">例如，六個系統管理員可能會有三個開啟的會話。</span><span class="sxs-lookup"><span data-stu-id="9aab5-180">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="9aab5-181">如果第七個系統管理員嘗試開啟超過兩個的連線（同時連接21個同時連線），則這項嘗試將會失敗，並顯示下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9aab5-181">If a seventh administrator tries to open more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="9aab5-182">**錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此租使用者的併發 shell 數上限。關閉現有的程式外殼程式，或升高此租使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*</span><span class="sxs-lookup"><span data-stu-id="9aab5-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="9aab5-183">**解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。</span><span class="sxs-lookup"><span data-stu-id="9aab5-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="9aab5-184">當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止該會話。</span><span class="sxs-lookup"><span data-stu-id="9aab5-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="9aab5-185">這將協助您避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="9aab5-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="9aab5-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="9aab5-186">Related topics</span></span>
[<span data-ttu-id="9aab5-187">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="9aab5-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

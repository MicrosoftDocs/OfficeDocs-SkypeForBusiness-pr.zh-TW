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
f1keywords: None
ms.custom:
- PowerShell
description: 疑難排解建立用來連線到商務用 Skype Online 的遠端 PowerShell 會話，包括匯入模組、併發 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: 863593c3068136f4b2332a55d8e0c293d2acc1d8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991308"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="0642c-103">診斷商務用 Skype Online 連接器的連線問題</span><span class="sxs-lookup"><span data-stu-id="0642c-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="0642c-104">本主題提供的資訊可協助您診斷並解決當您嘗試建立連線到商務用 Skype Online 的遠端 Microsoft PowerShell 會話時，可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="0642c-105">請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="0642c-105">See the following sections:</span></span>
  
- [<span data-ttu-id="0642c-106">Import-Windows PowerShell 執行原則所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="0642c-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="0642c-107">匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="0642c-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="0642c-108">已停用 WinRM 基本驗證時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="0642c-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- <span data-ttu-id="0642c-109">[無法連線至 [Live ID] 伺服器](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)</span><span class="sxs-lookup"><span data-stu-id="0642c-109">[Failed to connect to Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)</span></span>
    
- <span data-ttu-id="0642c-110">[無法載入 [實際 ID] 模組](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)</span><span class="sxs-lookup"><span data-stu-id="0642c-110">[Failed to load Live ID module](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)</span></span>
    
- [<span data-ttu-id="0642c-111">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="0642c-111">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="0642c-112">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="0642c-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="0642c-113">在商務用 Skype Online 中已停用連接至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="0642c-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="0642c-114">已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限</span><span class="sxs-lookup"><span data-stu-id="0642c-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="0642c-115">已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限</span><span class="sxs-lookup"><span data-stu-id="0642c-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="0642c-116">根據預設，PowerShell 會話會在60分鐘後超時。</span><span class="sxs-lookup"><span data-stu-id="0642c-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="0642c-117">若要重新連接，您必須關閉會話，然後啟動新的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0642c-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="0642c-118">新版本的[商務用 Skype Online （Windows PowerShell 模組（2046.123-已發佈的10/2/2019））](https://www.microsoft.com/download/details.aspx?id=39366)最近已啟動，其中包含一個名為**Enable-CsOnlineSessionForReconnection**的新 Cmdlet，可減少60分鐘超時問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="0642c-119">PowerShell 會話會重新連線並進行驗證，讓它得以重複使用，而不需啟動要重新連接的新實例。</span><span class="sxs-lookup"><span data-stu-id="0642c-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="0642c-120">Import-Windows PowerShell 執行原則所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="0642c-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="0642c-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-121"></span></span>

<span data-ttu-id="0642c-122">PowerShell 執行原則可協助判斷哪些設定檔可以載入到 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。</span><span class="sxs-lookup"><span data-stu-id="0642c-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="0642c-123">除非執行原則已設定為 RemoteSigned，否則在最低限度的情況下，無法匯入商務用 Skype Online 連接器模組。</span><span class="sxs-lookup"><span data-stu-id="0642c-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="0642c-124">如果沒有，當您嘗試匯入模組時，您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="0642c-125">**錯誤**：<em>匯入-模組：檔案 C\\： Program\\files 常見\\檔案 Microsoft Lync Server\\2013\\模組\\LyncOnlineConnector 無法載入 psm1，因為在這個系統上已停用執行腳本。如需詳細資訊，請參閱https://go.microsoft.com/fwlink/?LinkID=135170about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="0642c-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="0642c-126">**解析度**若要解決此問題，請以系統管理員的身分啟動 PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0642c-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="0642c-127">如需有關執行原則的詳細資訊，請參閱[關於執行](https://go.microsoft.com/fwlink/?LinkID=135170)原則。</span><span class="sxs-lookup"><span data-stu-id="0642c-127">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="0642c-128">匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤</span><span class="sxs-lookup"><span data-stu-id="0642c-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="0642c-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-129"></span></span>

<span data-ttu-id="0642c-130">商務用 Skype Online 連接器模組只能在 Windows PowerShell 3.0 下執行。</span><span class="sxs-lookup"><span data-stu-id="0642c-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="0642c-131">如果您嘗試在舊版 PowerShell 中匯入模組，匯入程式將會失敗，並顯示類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="0642c-132">**錯誤**：匯*入-模組：載入的 PowerShell 版本是 "2.0"。Module to\\： Program files\\常見檔案\\Microsoft Lync Server 2013\\模組\\LyncOnlineConnector\\LyncOnlineConnector，psd1 ' 需要最小3.0 的 PowerShell 版本才能執行。請確認已安裝 PowerShell，然後再試一次。*</span><span class="sxs-lookup"><span data-stu-id="0642c-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="0642c-133">**解決**方式：修正這個問題的唯一方法是安裝 Windows PowerShell 3.0，此版本可從 Microsoft 下載中心取得[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。</span><span class="sxs-lookup"><span data-stu-id="0642c-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="0642c-134">已停用 WinRM 基本驗證時，新式驗證失敗</span><span class="sxs-lookup"><span data-stu-id="0642c-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="0642c-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-135"></span></span>

<span data-ttu-id="0642c-136">最新版本的商務用 Skype Online 連接器模組使用新式驗證，但基礎 Windows 遠端系統管理（WinRM）用戶端必須設定為允許基本驗證。</span><span class="sxs-lookup"><span data-stu-id="0642c-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="0642c-137">新式驗證使用通常會在*授權：載荷*標頭中傳遞的載荷權杖。</span><span class="sxs-lookup"><span data-stu-id="0642c-137">Modern authentication uses bearer tokens which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="0642c-138">Windows PowerShell （在此建立商務用 Skype PowerShell）不允許操作此標頭。</span><span class="sxs-lookup"><span data-stu-id="0642c-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="0642c-139">相反地，商務用 Skype PowerShell 會使用*授權：基本*報頭來傳送載荷權杖。</span><span class="sxs-lookup"><span data-stu-id="0642c-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="0642c-140">如需有關如何啟用 WinRM 進行基本驗證的指示，請參閱[下載並安裝 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) 。</span><span class="sxs-lookup"><span data-stu-id="0642c-140">See [Download and install Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="0642c-141">無法連線至 [Live ID] 伺服器</span><span class="sxs-lookup"><span data-stu-id="0642c-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="0642c-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-142"></span></span>

<span data-ttu-id="0642c-143">使用下列錯誤訊息時，連接嘗試可能會失敗的原因有三種：</span><span class="sxs-lookup"><span data-stu-id="0642c-143">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="0642c-144">**錯誤**： *CsWebTicket：無法連接即時 id 伺服器。請確定已啟用 proxy，或電腦有連線至 live id 伺服器的網路連線。*</span><span class="sxs-lookup"><span data-stu-id="0642c-144">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="0642c-145">**解決**方式：此錯誤通常表示 Microsoft Online Services 登入小幫手未執行。</span><span class="sxs-lookup"><span data-stu-id="0642c-145">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="0642c-146">您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態：</span><span class="sxs-lookup"><span data-stu-id="0642c-146">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="0642c-147">如果服務未執行，請使用此命令啟動服務：</span><span class="sxs-lookup"><span data-stu-id="0642c-147">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="0642c-148">如果服務正在執行，您可能會遇到您的電腦與 Microsoft Live ID 驗證服務器之間的網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-148">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="0642c-149">若要檢查此情況，請開啟 Internet Explorer，然後流覽至[ https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="0642c-149">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="0642c-150">嘗試從該處登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0642c-150">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="0642c-151">如果這種情況失敗，可能是遇到網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-151">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="0642c-152">不太常見，Microsoft Live ID 驗證服務器的連線 URI 可能已設定為錯誤的值。</span><span class="sxs-lookup"><span data-stu-id="0642c-152">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="0642c-153">如果您已確定登入小幫手正在執行，而且您沒有網路連線問題，這可能是問題所在。</span><span class="sxs-lookup"><span data-stu-id="0642c-153">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="0642c-154">在這種情況下，請與 Office 365 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="0642c-154">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="0642c-155">無法載入 [實際 ID] 模組</span><span class="sxs-lookup"><span data-stu-id="0642c-155">Failed to load Live ID module</span></span>
<span data-ttu-id="0642c-156"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-156"></span></span>

<span data-ttu-id="0642c-157">使用 PowerShell 來管理商務用 Skype Online 的其中一個先決條件是安裝 Microsoft Online Services 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="0642c-157">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="0642c-158">如果未安裝登入小幫手，當您嘗試與商務用 Skype Online 建立遠端會話時，您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-158">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="0642c-159">**錯誤**： *CsWebTicket：無法載入 [即時 Id] 模組。請確定已安裝 [正確版本的 Live Id 登入*小幫手]。</span><span class="sxs-lookup"><span data-stu-id="0642c-159">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="0642c-160">**解析度**：適用于[IT 專業人員的 microsoft Online services 登入](https://www.microsoft.com/en-us/download/details.aspx?id=28177)小幫手，Microsoft 下載中心提供 microsoft online services 登入小幫手 RTW</span><span class="sxs-lookup"><span data-stu-id="0642c-160">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="0642c-161">使用者登入失敗</span><span class="sxs-lookup"><span data-stu-id="0642c-161">Logon failed for the user</span></span>
<span data-ttu-id="0642c-162"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-162"></span></span>

<span data-ttu-id="0642c-163">當您嘗試建立與商務用 Skype Online 的遠端連線時，您必須提供有效的商務用 Skype Online 使用者帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="0642c-163">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="0642c-164">如果您沒有這樣做，登入將會失敗，並會出現類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-164">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="0642c-165">**錯誤**： *CsWebTicket：使用者 ' kenmyer@litwareinc.com ' 登入失敗。請建立新的 PSCredential 物件，並確認您使用的是正確的使用者名稱和密碼。*</span><span class="sxs-lookup"><span data-stu-id="0642c-165">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="0642c-166">**解決方案**：如果您認為您使用的是有效的使用者帳戶，且您有正確的密碼，請嘗試再次登入。</span><span class="sxs-lookup"><span data-stu-id="0642c-166">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="0642c-167">如果失敗，請使用相同的認證，然後嘗試登入[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。</span><span class="sxs-lookup"><span data-stu-id="0642c-167">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="0642c-168">如果您無法登入，請與 Office 365 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="0642c-168">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="0642c-169">使用者沒有管理此租使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="0642c-169">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="0642c-170"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-170"></span></span>

<span data-ttu-id="0642c-171">除非您是租使用者管理員群組的成員，否則您無法建立商務用的遠端 PowerShell 連線 toSkype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="0642c-171">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="0642c-172">如果您不是這樣，您的連線嘗試將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-172">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="0642c-173">**錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用者 ' user@foo.com」沒有管理此租使用者的許可權。您可以將使用者指派給適當的 RBAC 角色，以授與許可權。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="0642c-173">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="0642c-174">**解決**方式：如果您認為您是（或應該是租使用者管理員群組的成員），您必須與 Office 365 支援人員取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="0642c-174">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="0642c-175">在商務用 Skype Online 中已停用連接至租使用者的能力</span><span class="sxs-lookup"><span data-stu-id="0642c-175">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="0642c-176"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-176"></span></span>

<span data-ttu-id="0642c-177">若要使用 PowerShell 來管理商務用 Skype Online，您必須將租使用者 PowerShell 原則的 EnableRemotePowerShellAccess 屬性設定`True`為。</span><span class="sxs-lookup"><span data-stu-id="0642c-177">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="0642c-178">如果不是，您的連線將會失敗，而且您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-178">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="0642c-179">**錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用遠端 PowerShell 會話連線到此租使用者的功能已停用。請聯絡 Lync 說明，以查看此租使用者的租使用者 Powershell 原則。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="0642c-179">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="0642c-180">**解決**方式：如果您看到這則錯誤訊息，您必須與 Office 365 支援人員取得聯繫，並啟用遠端 PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="0642c-180">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="0642c-181">已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限</span><span class="sxs-lookup"><span data-stu-id="0642c-181">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="0642c-182"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-182"></span></span>

<span data-ttu-id="0642c-183">每個系統管理員都允許最多三個同時遠端連線到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="0642c-183">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="0642c-184">如果您有三個遠端 PowerShell 連線且正在執行，則嘗試讓第四個同步連接的嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-184">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="0642c-185">**錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此使用者的併發 shell 數目上限。關閉現有的程式外殼程式，或升高此使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*</span><span class="sxs-lookup"><span data-stu-id="0642c-185">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="0642c-186">**解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。</span><span class="sxs-lookup"><span data-stu-id="0642c-186">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="0642c-187">當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止會話。</span><span class="sxs-lookup"><span data-stu-id="0642c-187">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="0642c-188">這將協助您避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-188">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="0642c-189">已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限</span><span class="sxs-lookup"><span data-stu-id="0642c-189">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="0642c-190"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="0642c-190"></span></span>

<span data-ttu-id="0642c-191">雖然每個系統管理員都允許有多達三個同時連線至商務用 Skype Online 租使用者，但不允許單一租使用者同時連接20個以上的連線。</span><span class="sxs-lookup"><span data-stu-id="0642c-191">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="0642c-192">例如，六個系統管理員可能會有三個開啟的會話。</span><span class="sxs-lookup"><span data-stu-id="0642c-192">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="0642c-193">如果第四個系統管理員嘗試進行超過2個連線（導致總共有21個同時連線），此嘗試將會失敗，並出現下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0642c-193">If a fourth administrator tries to make more than 2 connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="0642c-194">**錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此租使用者的併發 shell 數上限。關閉現有的程式外殼程式，或升高此租使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*</span><span class="sxs-lookup"><span data-stu-id="0642c-194">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="0642c-195">**解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。</span><span class="sxs-lookup"><span data-stu-id="0642c-195">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="0642c-196">當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止該會話。</span><span class="sxs-lookup"><span data-stu-id="0642c-196">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="0642c-197">這將協助您避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="0642c-197">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="0642c-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="0642c-198">Related topics</span></span>
[<span data-ttu-id="0642c-199">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="0642c-199">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

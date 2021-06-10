---
title: 準備您的環境
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 瞭解如何準備基礎結構以部署Microsoft Teams 會議室，以便利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117421"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="a4834-103">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="a4834-103">Prepare your environment</span></span>

<span data-ttu-id="a4834-104">本節包含準備環境所需的步驟概觀，以便您可以使用所有Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="a4834-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="a4834-105">準備每個主機的裝置Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="a4834-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="a4834-106">請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)以尋找詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4834-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="a4834-107">請確保裝置有可使用的網路/網際網路連接。</span><span class="sxs-lookup"><span data-stu-id="a4834-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="a4834-108">它必須能夠使用 DHCP 接收 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4834-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="a4834-109"> (Microsoft Teams 會議室裝置啟動時無法使用靜態 IP 位址進行配置，但之後，裝置上的靜態 IP 位址可以在裝置上或上行交換器或路由器上) </span><span class="sxs-lookup"><span data-stu-id="a4834-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="a4834-110">除了開啟媒體的一般 (之外，還必須開啟這些埠) ：</span><span class="sxs-lookup"><span data-stu-id="a4834-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="a4834-111">HTTPS：443</span><span class="sxs-lookup"><span data-stu-id="a4834-111">HTTPS: 443</span></span>
   - <span data-ttu-id="a4834-112">HTTP：80</span><span class="sxs-lookup"><span data-stu-id="a4834-112">HTTP: 80</span></span>

   <span data-ttu-id="a4834-113">如果您的網路是透過 Proxy 執行，您也需要 Proxy 位址或腳本資訊。</span><span class="sxs-lookup"><span data-stu-id="a4834-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="a4834-114">Microsoft Teams 會議室不支援 Proxy 驗證，因為它可能會干擾會議室的一般作業。</span><span class="sxs-lookup"><span data-stu-id="a4834-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="a4834-115">在投入Microsoft Teams 會議室之前，請確保已免除 Proxy 驗證。</span><span class="sxs-lookup"><span data-stu-id="a4834-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="a4834-116">為了改善您的體驗，Microsoft 會收集資料。</span><span class="sxs-lookup"><span data-stu-id="a4834-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="a4834-117">若要允許 Microsoft 收集資料，請允許這些網站：</span><span class="sxs-lookup"><span data-stu-id="a4834-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="a4834-118">遙測用戶端端點： https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="a4834-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="a4834-119">遙測設定端點： https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="a4834-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="a4834-120">建立和測試裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="a4834-120">Create and test a device account</span></span>

<span data-ttu-id="a4834-121">裝置 *帳戶* 是用戶端用來從 Microsoft Teams 會議室 存取功能的帳戶，Exchange例如日曆，以及啟用商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="a4834-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="a4834-122">請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)以尋找詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4834-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="a4834-123">檢查網路可用性</span><span class="sxs-lookup"><span data-stu-id="a4834-123">Check network availability</span></span>

<span data-ttu-id="a4834-124">若要正常運作，Microsoft Teams 會議室裝置必須能夠存取符合這些要求的有線網路：</span><span class="sxs-lookup"><span data-stu-id="a4834-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="a4834-125">存取 Active Directory 或 Azure Active Directory (Azure AD) 實例，以及您的 Microsoft Exchange 商務用 Skype伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4834-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="a4834-126">存取可以使用 DHCP 提供 IP 位址的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4834-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="a4834-127">Microsoft Teams 會議室第一次裝置啟動時，無法使用靜態 IP 位址來進行配置。</span><span class="sxs-lookup"><span data-stu-id="a4834-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="a4834-128">存取 HTTP 埠 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="a4834-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="a4834-129">如內部部署 商務用 Skype Server 實現或 Microsoft 365[](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)和 Office 365 URL 與[IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)位址範圍之內部部署 商務用 Skype Server 的埠和通訊協定需求所述，為 Microsoft Teams 或 商務用 Skype 線上實現所配置的 TCP 和 UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="a4834-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4834-130">請務必使用有線 1Gbps 網路連接，以確保您擁有所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="a4834-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="a4834-131">系統會自動從 Microsoft Teams 會議室 下載適用于 商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="a4834-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="a4834-132">請參閱[商務用 Microsoft Store與教育](/microsoft-store/prerequisites-microsoft-store-for-business)的先決條件，以驗證會議室主控台是否能夠存取儲存空間並自我更新。</span><span class="sxs-lookup"><span data-stu-id="a4834-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="a4834-133">證書</span><span class="sxs-lookup"><span data-stu-id="a4834-133">Certificates</span></span>

<span data-ttu-id="a4834-134">您的Microsoft Teams 會議室會使用憑證Exchange Web Services、Microsoft Teams或商務用 Skype、網路使用方式和驗證。</span><span class="sxs-lookup"><span data-stu-id="a4834-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="a4834-135">如果相關伺服器使用公用憑證 ，例如 Online 和部分內部部署，則系統管理員無需執行其他動作來安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="a4834-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="a4834-136">另一方面，如果憑證頒發機構是私人 CA (通常是內部部署) 則裝置必須信任該 CA，這表示裝置上安裝 CA + CA 鏈證書。</span><span class="sxs-lookup"><span data-stu-id="a4834-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="a4834-137">將裝置新加入網域可能會自動執行這項工作。</span><span class="sxs-lookup"><span data-stu-id="a4834-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="a4834-138">您安裝憑證的方式，與安裝任何其他用戶端Windows相同。</span><span class="sxs-lookup"><span data-stu-id="a4834-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a4834-139">您可能需要憑證才能Microsoft Teams 會議室使用商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="a4834-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="a4834-140">代理</span><span class="sxs-lookup"><span data-stu-id="a4834-140">Proxy</span></span>

<span data-ttu-id="a4834-141">Microsoft Teams 會議室是從作業系統繼承 Proxy Windows設定。</span><span class="sxs-lookup"><span data-stu-id="a4834-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="a4834-142">以下列Windows存取作業系統：</span><span class="sxs-lookup"><span data-stu-id="a4834-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="a4834-143">在 Microsoft Teams 會議室 UI 中，按一下 設定 齒輪圖示，系統會提示您輸入裝置上的當地系統管理員密碼 (預設密碼為 **sfb**) 。</span><span class="sxs-lookup"><span data-stu-id="a4834-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="a4834-144">點 **選 設定，** 然後點選前往 **Windows** 按鈕，然後點選前往系統管理登錄按鈕，然後按一下管理員按鈕 (如果電腦已加入網域，請選擇其他使用者，然後使用 .\admin 做為使用者名稱) 。 </span><span class="sxs-lookup"><span data-stu-id="a4834-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="a4834-145">在 [**搜尋Windows** 方塊左下輸入 regedit (長按螢幕或以滑鼠右鍵按一下，然後選擇 [以系統管理員) 。</span><span class="sxs-lookup"><span data-stu-id="a4834-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="a4834-146">按一下 [HKEY_USERS資料夾 (，就會看到電腦使用者 SID 清單，) 已選取HKEY_USERS資料夾。</span><span class="sxs-lookup"><span data-stu-id="a4834-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="a4834-147">按一下 [檔案>，然後選擇 [ **載入配置單元。**</span><span class="sxs-lookup"><span data-stu-id="a4834-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="a4834-148">流覽至 **C：\Users\Skype** 資料夾，然後輸入 NTUSER.dat 的檔案名方塊，然後按開啟按鈕</span><span class="sxs-lookup"><span data-stu-id="a4834-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="a4834-149">系統會提示您為新載入的 Hive 輸入 Key Name;輸入Skype (，您現在應該會看到使用者帳戶的登錄Skype) 。</span><span class="sxs-lookup"><span data-stu-id="a4834-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="a4834-150">開啟Skype鍵並流覽至HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然後確保已輸入這些設定：</span><span class="sxs-lookup"><span data-stu-id="a4834-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="a4834-151">如果 ProxyServer 不存在，您可能需要將此金鑰新增為字串，將 xx.xx.xx.xx：8080 變更為 Proxy 伺服器的 ip/host 和埠。</span><span class="sxs-lookup"><span data-stu-id="a4834-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="a4834-152">如果客戶使用 PAC 檔案，該組組看起來會類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="a4834-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="a4834-153">完成變更後，請為 Skype) 的 Skype 使用者金鑰 (根資料夾加亮，然後選擇從登錄檔案功能表卸載 Hive (系統會提示您確認 - 選取是) 。 </span><span class="sxs-lookup"><span data-stu-id="a4834-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="a4834-154">現在，您可以關閉登錄編輯器，然後輸入登入 Windows方塊。</span><span class="sxs-lookup"><span data-stu-id="a4834-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="a4834-155">回到登錄畫面，選擇 **Skype使用者。**</span><span class="sxs-lookup"><span data-stu-id="a4834-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="a4834-156">如果上述所有步驟都成功，Microsoft Teams 會議室裝置會順利登錄。</span><span class="sxs-lookup"><span data-stu-id="a4834-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="a4834-157">請參閱[網路安全性](./security.md#network-security)文章，以進一步瞭解 FQDNs、埠和 IP 位址範圍Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="a4834-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="a4834-158">建立部署套件</span><span class="sxs-lookup"><span data-stu-id="a4834-158">Create provisioning packages</span></span>

<span data-ttu-id="a4834-159">您將使用部署套件來驗證Exchange Server、Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="a4834-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="a4834-160">系統管理群組管理</span><span class="sxs-lookup"><span data-stu-id="a4834-160">Admin group management</span></span>

<span data-ttu-id="a4834-161">加入網域之後，您可以使用群組原則或本地電腦管理將安全性群組設定為本地系統管理員，就像您網域Windows電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="a4834-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="a4834-162">任何加入該安全性群組的人都可以輸入其認證，並解除設定。</span><span class="sxs-lookup"><span data-stu-id="a4834-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4834-163">如果您的 Microsoft Teams 會議室 裝置與網域 (失去信任，例如，如果您在網域加入) 後從網域移除 Microsoft Teams 會議室，您將無法驗證至裝置並開啟 設定。</span><span class="sxs-lookup"><span data-stu-id="a4834-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="a4834-164">解決方法是使用本地系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a4834-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="a4834-165">本地帳戶</span><span class="sxs-lookup"><span data-stu-id="a4834-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="a4834-166">Microsoft Teams 會議室本地使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a4834-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="a4834-167">裝置帳戶通常不會使用密碼。</span><span class="sxs-lookup"><span data-stu-id="a4834-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="a4834-168">您可以為它輸入密碼，但會產生一些後果，包括使用者可能在密碼到期時被鎖定在主控台應用程式外。</span><span class="sxs-lookup"><span data-stu-id="a4834-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="a4834-169">因此，系統管理員應該採取一些措施，確保密碼不會過期。</span><span class="sxs-lookup"><span data-stu-id="a4834-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="a4834-170">「系統管理員」- 本地系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="a4834-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="a4834-171">Microsoft Teams 會議室預設密碼設為"sfb"。</span><span class="sxs-lookup"><span data-stu-id="a4834-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="a4834-172">您可以前往 Windows 設定 前往 Windows 或 AutoUnattend.xml 檔案 (使用 ADK 的 Windows System Image manager 變更 xml 檔案) 。 \></span><span class="sxs-lookup"><span data-stu-id="a4834-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a4834-173">請務必儘快變更Microsoft Teams 會議室密碼。</span><span class="sxs-lookup"><span data-stu-id="a4834-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="a4834-174">您也可以設定群組原則，將網域系統管理員設定為本地系統管理員，以管理本地系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="a4834-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="a4834-175">在設定期間，系統不會提供本地系統管理員密碼做為選項。</span><span class="sxs-lookup"><span data-stu-id="a4834-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="a4834-176">電腦帳戶</span><span class="sxs-lookup"><span data-stu-id="a4834-176">Machine Account</span></span>

<span data-ttu-id="a4834-177">就像任何Windows裝置一樣，以滑鼠右鍵按一下關於重新命名電腦設定 \>  \> **名稱**。</span><span class="sxs-lookup"><span data-stu-id="a4834-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="a4834-178">如果您想要在將電腦加入網域後重新命名，請使用 **重新命名電腦**，這是 PowerShell 命令，後面接著電腦的新名稱。</span><span class="sxs-lookup"><span data-stu-id="a4834-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a4834-179">相關主題</span><span class="sxs-lookup"><span data-stu-id="a4834-179">Related topics</span></span>

[<span data-ttu-id="a4834-180">規劃Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="a4834-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="a4834-181">Microsoft Teams 會議室需求</span><span class="sxs-lookup"><span data-stu-id="a4834-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="a4834-182">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="a4834-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="a4834-183">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="a4834-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a4834-184">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="a4834-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="a4834-185">教育商務用 Microsoft Store的先決條件</span><span class="sxs-lookup"><span data-stu-id="a4834-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)
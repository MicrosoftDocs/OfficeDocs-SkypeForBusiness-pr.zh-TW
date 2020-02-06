---
title: 在商務用 Skype Server 中設定雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在商務用 Skype Server 中設定雙因素驗證。
ms.openlocfilehash: 40749cbe3e0bf50a6ff6a640038d63d4a4479b7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818815"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="34193-103">在商務用 Skype Server 中設定雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="34193-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="34193-104">**摘要：** 在商務用 Skype Server 中設定雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="34193-105">下列各節說明針對您的部署設定雙因素驗證所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="34193-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="34193-106">如需有關雙因素驗證的詳細資訊，請參閱[啟用 Office 365 的多重要素驗證以進行線上系統管理員-格線使用者文章](https://go.microsoft.com/fwlink/p/?LinkId=313332)。</span><span class="sxs-lookup"><span data-stu-id="34193-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="34193-107">設定企業根憑證授權單位以支援智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="34193-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="34193-108">下列步驟說明如何將企業根 CA 設定為支援智慧卡驗證：</span><span class="sxs-lookup"><span data-stu-id="34193-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="34193-109">如需如何安裝企業根 CA 的詳細資訊，請參閱[安裝企業根憑證授權單位](https://go.microsoft.com/fwlink/p/?LinkID=313364)。</span><span class="sxs-lookup"><span data-stu-id="34193-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="34193-110">使用網域系統管理員帳戶登入企業 CA 電腦。</span><span class="sxs-lookup"><span data-stu-id="34193-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="34193-111">啟動系統管理員，然後確認已安裝憑證授權單位 Web 登記角色。</span><span class="sxs-lookup"><span data-stu-id="34193-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="34193-112">從 [**管理工具**] 功能表，開啟 [**認證機構**管理] 主控台。</span><span class="sxs-lookup"><span data-stu-id="34193-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="34193-113">在 [功能窗格] 中，展開 [**憑證授權單位**]。</span><span class="sxs-lookup"><span data-stu-id="34193-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="34193-114">以滑鼠右鍵按一下**憑證範本**，選取 [**新增**]，然後選取 [**要頒發的憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="34193-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="34193-115">選取 [**註冊代理程式**、**智慧卡使用者**和**智慧卡登**入]。</span><span class="sxs-lookup"><span data-stu-id="34193-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="34193-116">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34193-116">Click **OK**.</span></span>

8. <span data-ttu-id="34193-117">以滑鼠右鍵按一下**憑證範本**。</span><span class="sxs-lookup"><span data-stu-id="34193-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="34193-118">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="34193-118">Select **Manage**.</span></span>

10. <span data-ttu-id="34193-119">開啟 [智慧卡] 使用者範本的屬性。</span><span class="sxs-lookup"><span data-stu-id="34193-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="34193-120">按一下 [**安全性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="34193-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="34193-121">變更許可權，如下所示：</span><span class="sxs-lookup"><span data-stu-id="34193-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="34193-122">新增具有讀取/註冊（允許）許可權的個別使用者廣告帳戶，或</span><span class="sxs-lookup"><span data-stu-id="34193-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="34193-123">新增包含具有讀取/註冊（允許）許可權的智慧卡使用者的安全性群組，或</span><span class="sxs-lookup"><span data-stu-id="34193-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="34193-124">新增具有讀取/註冊（允許）許可權的 [網域使用者] 群組</span><span class="sxs-lookup"><span data-stu-id="34193-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="34193-125">針對虛擬智慧卡設定 Windows 8</span><span class="sxs-lookup"><span data-stu-id="34193-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="34193-126">部署雙因素驗證與智慧卡技術時，要考慮的一個因素是實施成本。</span><span class="sxs-lookup"><span data-stu-id="34193-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="34193-127">Windows 8 提供許多新的安全性功能，其中一個最有趣的新功能就是支援虛擬智慧卡。</span><span class="sxs-lookup"><span data-stu-id="34193-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="34193-128">對於配備符合規範版本1.2 的可信平臺模組（TPM）晶片的電腦，組織現在可以取得智慧卡登入的優點，而不需要在硬體中進行任何額外的投資。</span><span class="sxs-lookup"><span data-stu-id="34193-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="34193-129">如需詳細資訊，請參閱[在 Windows 8 中使用虛擬智慧卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。</span><span class="sxs-lookup"><span data-stu-id="34193-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="34193-130">針對虛擬智慧卡設定 Windows 8</span><span class="sxs-lookup"><span data-stu-id="34193-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="34193-131">使用商務用 Skype 使用者的認證登入 Windows 8 電腦。</span><span class="sxs-lookup"><span data-stu-id="34193-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="34193-132">在 Windows 8 的 [開始] 畫面中，將游標移至畫面的右下角。</span><span class="sxs-lookup"><span data-stu-id="34193-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="34193-133">選取 [**搜尋**] 選項，然後搜尋 [forCommand 提示]。</span><span class="sxs-lookup"><span data-stu-id="34193-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="34193-134">以滑鼠右鍵按一下**命令提示**字元，然後選取 [以**系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="34193-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="34193-135">執行下列命令以開啟可信平臺模組（TPM）管理主控台：</span><span class="sxs-lookup"><span data-stu-id="34193-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="34193-136">從 TPM 管理主控台，確認您的 TPM 規格版本至少為1。2</span><span class="sxs-lookup"><span data-stu-id="34193-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="34193-137">如果您收到對話方塊，指出找不到相容的信任平臺模組（TPM），請確認電腦有相容的 TPM 模組，且已在系統 BIOS 中啟用。</span><span class="sxs-lookup"><span data-stu-id="34193-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="34193-138">關閉 TPM 管理主控台</span><span class="sxs-lookup"><span data-stu-id="34193-138">Close the TPM management console</span></span>

8. <span data-ttu-id="34193-139">在命令提示字元中，使用下列命令建立新的虛擬智慧卡：</span><span class="sxs-lookup"><span data-stu-id="34193-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="34193-140">若要在建立虛擬智慧卡時提供自訂 PIN 值，請改為使用/pin 提示。</span><span class="sxs-lookup"><span data-stu-id="34193-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="34193-141">在命令提示字元中，執行下列命令以開啟 [電腦管理] 主控台：</span><span class="sxs-lookup"><span data-stu-id="34193-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="34193-142">在 [電腦管理] 主控台中，選取 [**裝置管理**]。</span><span class="sxs-lookup"><span data-stu-id="34193-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="34193-143">展開 [**智慧卡讀取器**]。</span><span class="sxs-lookup"><span data-stu-id="34193-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="34193-144">確認已成功建立新的虛擬智慧卡讀卡機。</span><span class="sxs-lookup"><span data-stu-id="34193-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="34193-145">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="34193-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="34193-146">有兩種方法可以為使用者註冊智慧卡驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="34193-147">更簡單的方法是讓使用者使用 web 註冊直接註冊智慧卡驗證，而更複雜的方法則涉及使用註冊代理程式。</span><span class="sxs-lookup"><span data-stu-id="34193-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="34193-148">本主題主要針對智慧卡憑證的自行註冊。</span><span class="sxs-lookup"><span data-stu-id="34193-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="34193-149">如需將使用者註冊為註冊代理程式的詳細資訊，請參閱[代表其他使用者註冊證書](https://go.microsoft.com/fwlink/p/?LinkID=313367)。</span><span class="sxs-lookup"><span data-stu-id="34193-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="34193-150">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="34193-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="34193-151">使用商務用 Skype 使用者的認證登入 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="34193-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="34193-152">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="34193-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="34193-153">流覽至 [**憑證授權單位 Web 註冊**] 頁面（ https://MyCA.contoso.com/certsrv)例如</span><span class="sxs-lookup"><span data-stu-id="34193-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="34193-154">如果您使用的是 Internet Explorer 10，您可能需要以相容模式查看此網站。</span><span class="sxs-lookup"><span data-stu-id="34193-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="34193-155">在 [**歡迎**] 頁面上，選取 [**要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="34193-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="34193-156">接著，選取 [**高級要求**]。</span><span class="sxs-lookup"><span data-stu-id="34193-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="34193-157">選取 [**建立並提交此 CA 的要求**]。</span><span class="sxs-lookup"><span data-stu-id="34193-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="34193-158">選取 [**憑證範本**] 區段底下的 [**智慧卡使用者**]，並以下列值完成高級憑證要求：</span><span class="sxs-lookup"><span data-stu-id="34193-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="34193-159">[**主要選項**] 請確認他追蹤下列設定：</span><span class="sxs-lookup"><span data-stu-id="34193-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="34193-160">選取 [**建立新金鑰集**] 選項按鈕</span><span class="sxs-lookup"><span data-stu-id="34193-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="34193-161">針對**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]</span><span class="sxs-lookup"><span data-stu-id="34193-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="34193-162">如需**金鑰用法**，請選取 [ **Exchange** ] （這是唯一可用的選項）。</span><span class="sxs-lookup"><span data-stu-id="34193-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="34193-163">針對**金鑰大小**，請輸入2048</span><span class="sxs-lookup"><span data-stu-id="34193-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="34193-164">確認已選取 [**自動金鑰容器名稱**]</span><span class="sxs-lookup"><span data-stu-id="34193-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="34193-165">不要選取其他方塊。</span><span class="sxs-lookup"><span data-stu-id="34193-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="34193-166">在 [**其他選項**] 底下，確認下列值：</span><span class="sxs-lookup"><span data-stu-id="34193-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="34193-167">針對**要求格式**，請選取 [ **CMC**]。</span><span class="sxs-lookup"><span data-stu-id="34193-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="34193-168">針對**雜湊演算法**選取 [ **sha1**]。</span><span class="sxs-lookup"><span data-stu-id="34193-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="34193-169">針對**易記的名稱**enterSmardcard 憑證。</span><span class="sxs-lookup"><span data-stu-id="34193-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="34193-170">如果您使用的是物理智慧卡讀取器，請將智慧卡插入裝置中。</span><span class="sxs-lookup"><span data-stu-id="34193-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="34193-171">按一下 [**提交**] 以提交證書申請。</span><span class="sxs-lookup"><span data-stu-id="34193-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="34193-172">出現提示時，請輸入用來建立虛擬智慧卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="34193-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="34193-173">預設的虛擬智慧卡 PIN 值是 "12345678"。</span><span class="sxs-lookup"><span data-stu-id="34193-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="34193-174">在頒發憑證之後，按一下 [**安裝此憑證**] 以完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="34193-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="34193-175">如果您的憑證要求失敗，並出現「此網頁瀏覽器不支援產生憑證要求」錯誤，有三種可能的方法可以解決此問題：</span><span class="sxs-lookup"><span data-stu-id="34193-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="34193-176">設定 Active Directory Federation Services （AD FS 2.0）</span><span class="sxs-lookup"><span data-stu-id="34193-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="34193-177">下列章節說明如何設定 Active Directory 同盟服務（AD FS 2.0）以支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="34193-178">如需如何安裝 AD FS 2.0 的詳細資訊，請參閱[AD fs 2.0 逐步說明和操作指南](https://go.microsoft.com/fwlink/p/?LinkId=313374)。</span><span class="sxs-lookup"><span data-stu-id="34193-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="34193-179">安裝 AD FS 2.0 時，請不要使用 Windows Server Manager 來新增 Active Directory 同盟服務角色。</span><span class="sxs-lookup"><span data-stu-id="34193-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="34193-180">相反地，請下載並安裝[Active Directory Federation Services 2.0 RTW 套件](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="34193-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="34193-181">針對雙因素驗證設定 AD FS</span><span class="sxs-lookup"><span data-stu-id="34193-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="34193-182">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="34193-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="34193-183">啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="34193-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="34193-184">從 [Windows PowerShell] 命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="34193-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="34193-185">您可以執行下列命令，以取代您的部署所專用的伺服器名稱，建立與每個伺服器的合作關係，以進行被動式驗證：</span><span class="sxs-lookup"><span data-stu-id="34193-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="34193-186">從 [管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="34193-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="34193-187">展開 [**信任關聯** > 性**信賴方信任**]。</span><span class="sxs-lookup"><span data-stu-id="34193-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="34193-188">確認已為您的商務用 Skype 伺服器建立新的信任。</span><span class="sxs-lookup"><span data-stu-id="34193-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="34193-189">若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行授權規則：</span><span class="sxs-lookup"><span data-stu-id="34193-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="34193-190">若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行轉換規則：</span><span class="sxs-lookup"><span data-stu-id="34193-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="34193-191">從 AD FS 2.0 管理主控台，以滑鼠右鍵按一下您的信賴方信任，然後選取 [**編輯宣告規則**]。</span><span class="sxs-lookup"><span data-stu-id="34193-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="34193-192">選取 [**發佈授權規則**] 索引標籤，並確認已成功建立新的授權規則。</span><span class="sxs-lookup"><span data-stu-id="34193-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="34193-193">選取 [**頒發轉換規則**] 索引標籤，並確認已成功建立新的轉換規則。</span><span class="sxs-lookup"><span data-stu-id="34193-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="34193-194">設定 AD FS 2.0 以支援用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="34193-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="34193-195">有兩種可能的驗證類型可以設定為允許 AD FS 2.0 使用智慧卡支援驗證：</span><span class="sxs-lookup"><span data-stu-id="34193-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="34193-196">以表單為基礎的驗證（FBA）</span><span class="sxs-lookup"><span data-stu-id="34193-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="34193-197">傳輸層安全性用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="34193-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="34193-198">使用以表單為基礎的驗證，您可以開發網頁，讓使用者可以使用他們的使用者名稱/密碼或使用其智慧卡和 PIN 來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="34193-199">本主題重點說明如何使用 AD FS 2.0 來實現傳輸層安全性用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="34193-200">如需有關 AD FS 2.0 驗證類型的詳細資訊，請參閱[AD fs 2.0：如何變更本機驗證類型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。</span><span class="sxs-lookup"><span data-stu-id="34193-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="34193-201">設定 AD FS 2.0 以支援用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="34193-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="34193-202">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="34193-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="34193-203">啟動 Windows 資源管理器。</span><span class="sxs-lookup"><span data-stu-id="34193-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="34193-204">流覽至 C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="34193-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="34193-205">製作現有 web.config 檔案的備份複本。</span><span class="sxs-lookup"><span data-stu-id="34193-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="34193-206">使用記事本開啟現有的 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="34193-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="34193-207">從功能表列中，選取 [**編輯**]，然後選取 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="34193-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="34193-208">搜尋\<localAuthenticationTypes\>。</span><span class="sxs-lookup"><span data-stu-id="34193-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="34193-209">請注意，列出四個驗證類型，每行一個。</span><span class="sxs-lookup"><span data-stu-id="34193-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="34193-210">將包含 TLSClient 驗證類型的行移至區段中清單的頂端。</span><span class="sxs-lookup"><span data-stu-id="34193-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="34193-211">儲存並關閉 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="34193-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="34193-212">以較高的許可權啟動命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="34193-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="34193-213">執行下列命令以重新開機 IIS：</span><span class="sxs-lookup"><span data-stu-id="34193-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="34193-214">設定商務用 Skype Server 被動式驗證</span><span class="sxs-lookup"><span data-stu-id="34193-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="34193-215">下列章節說明如何設定商務用 Skype Server 以支援被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="34193-216">一旦啟用，即會要求啟用雙因素驗證的使用者使用物理或虛擬智慧卡和有效的 PIN 來使用商務用 Skype 用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="34193-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="34193-217">強烈建議客戶針對服務層級的註冊機構和 Web 服務啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="34193-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="34193-218">如果針對全域層級的註冊機構和 Web 服務啟用被動式驗證，可能會導致不是以支援的桌面用戶端登入的使用者進行組織範圍的驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="34193-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="34193-219">Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="34193-219">Web Service Configuration</span></span>

<span data-ttu-id="34193-220">下列步驟說明如何為控制器、企業版池和標準版伺服器（將為被動驗證啟用）建立自訂的 web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="34193-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="34193-221">建立自訂的 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="34193-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="34193-222">使用商務用 Skype 系統管理員帳戶登入商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="34193-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="34193-223">啟動商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="34193-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="34193-224">從商務用 Skype Server Management Shell 命令列，為每個主管、企業版池及標準版伺服器建立新的 Web 服務設定，只要執行下列命令，即可啟用被動式驗證：</span><span class="sxs-lookup"><span data-stu-id="34193-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="34193-225">WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 伺服器的識別身分同盟服務名稱。</span><span class="sxs-lookup"><span data-stu-id="34193-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="34193-226">在 AD FS 2.0 管理主控台中，您可以在 [功能窗格] 中以滑鼠右鍵按一下 [**服務**]，然後選取 [**編輯同盟服務屬性**]，找到 [同盟服務名稱] 值。</span><span class="sxs-lookup"><span data-stu-id="34193-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="34193-227">執行下列命令，確認已正確設定 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：</span><span class="sxs-lookup"><span data-stu-id="34193-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="34193-228">針對用戶端，被動式驗證是 webticket 驗證的最不可取的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="34193-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="34193-229">針對所有要啟用被動式驗證的控制器、企業版池及標準版伺服器，您必須透過執行下列 Cmdlet，在商務用 Skype Web Services 中停用所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="34193-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="34193-230">執行下列 Cmdlet，確認所有其他驗證類型都已成功停用：</span><span class="sxs-lookup"><span data-stu-id="34193-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="34193-231">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="34193-231">Proxy Configuration</span></span>

<span data-ttu-id="34193-232">針對商務用 Skype Web 服務停用證書驗證時，商務用 Skype 用戶端會使用較不可取的喜好驗證類型（例如 Kerberos 或 NTLM）來驗證註冊機構服務。</span><span class="sxs-lookup"><span data-stu-id="34193-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="34193-233">您仍需要證書驗證來允許用戶端檢索 webticket，不過，必須針對註冊機構服務停用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="34193-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="34193-234">下列步驟說明如何針對要啟用被動式驗證的邊緣池、企業版池及標準版伺服器建立自訂 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="34193-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="34193-235">建立自訂 proxy 配置</span><span class="sxs-lookup"><span data-stu-id="34193-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="34193-236">從商務用 Skype Server Management Shell 命令列中，為每個商務用 Skype Server Edge 池、企業版池及標準版伺服器建立新的 proxy 設定，只要執行下列動作就能啟用被動式驗證指令</span><span class="sxs-lookup"><span data-stu-id="34193-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="34193-237">執行下列命令，確認所有其他 proxy 驗證類型都已順利停用：</span><span class="sxs-lookup"><span data-stu-id="34193-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="34193-238">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34193-238">See also</span></span>

[<span data-ttu-id="34193-239">在商務用 Skype Server 中管理雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="34193-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="34193-240">在商務用 Skype 用戶端和商務用 Skype Server 上使用雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="34193-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)

---
title: 在商務用 Skype Server 中設定雙因素驗證
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814413"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="4244d-103">在商務用 Skype Server 中設定雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="4244d-104">**摘要：** 在商務用 Skype Server 中設定雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="4244d-105">下列各節說明為您的部署設定雙因素驗證所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="4244d-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="4244d-106">如需有關雙因素驗證的詳細資訊，請參閱 [啟用 Office 365 多重要素驗證以供線上系統管理員格線使用者開機自檢](https://go.microsoft.com/fwlink/p/?LinkId=313332)。</span><span class="sxs-lookup"><span data-stu-id="4244d-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="4244d-107">設定企業根憑證授權以支援智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="4244d-108">下列步驟說明如何設定企業根 CA 以支援智慧卡驗證：</span><span class="sxs-lookup"><span data-stu-id="4244d-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="4244d-109">如需如何安裝企業根 CA 的詳細資訊，請參閱 [install a Enterprise Root 核證機關](https://go.microsoft.com/fwlink/p/?LinkID=313364)。</span><span class="sxs-lookup"><span data-stu-id="4244d-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="4244d-110">使用網域管理員帳戶登入 Enterprise CA 電腦。</span><span class="sxs-lookup"><span data-stu-id="4244d-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="4244d-111">啟動系統管理員，並確認已安裝 [憑證授權單位網站] 註冊角色。</span><span class="sxs-lookup"><span data-stu-id="4244d-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="4244d-112">在 [系統 **管理工具** ] 功能表中，開啟 [ **憑證授權單位** 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="4244d-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="4244d-113">在功能窗格中，展開 [ **憑證授權單位** 單位]。</span><span class="sxs-lookup"><span data-stu-id="4244d-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="4244d-114">以滑鼠右鍵按一下 [ **憑證範本**]，選取 [ **新增**]，然後選取 [ **要發出的憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="4244d-115">選取 [ **註冊代理程式**、 **智慧卡使用者** 及 **智慧卡登** 入]。</span><span class="sxs-lookup"><span data-stu-id="4244d-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="4244d-116">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4244d-116">Click **OK**.</span></span>

8. <span data-ttu-id="4244d-117">以滑鼠右鍵按一下 [ **憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="4244d-118">選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-118">Select **Manage**.</span></span>

10. <span data-ttu-id="4244d-119">開啟智慧卡使用者範本的屬性。</span><span class="sxs-lookup"><span data-stu-id="4244d-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="4244d-120">按一下 [ **安全性** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4244d-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="4244d-121">變更許可權，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4244d-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="4244d-122">使用讀取/註冊，新增個別使用者的 AD 帳戶。 (允許) 許可權，或</span><span class="sxs-lookup"><span data-stu-id="4244d-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="4244d-123">使用讀取/註冊，新增包含智慧卡使用者的安全性群組。 (允許) 許可權，或</span><span class="sxs-lookup"><span data-stu-id="4244d-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="4244d-124">新增具有讀取/註冊的網域使用者群組 (允許) 許可權</span><span class="sxs-lookup"><span data-stu-id="4244d-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="4244d-125">設定虛擬智慧卡的 Windows 8</span><span class="sxs-lookup"><span data-stu-id="4244d-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="4244d-126">部署雙因素驗證和智慧卡技術時，要考慮的一個因素是實施成本。</span><span class="sxs-lookup"><span data-stu-id="4244d-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="4244d-127">Windows 8 提供許多新的安全性功能，其中一個最有意思的新功能是支援虛擬智慧卡。</span><span class="sxs-lookup"><span data-stu-id="4244d-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="4244d-128">針對配備受信任平臺模組的電腦 (符合規格版本1.2 的 TPM) 晶片，組織現在可以取得智慧卡登入的優勢，而不需要在硬體上進行任何額外的投資。</span><span class="sxs-lookup"><span data-stu-id="4244d-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="4244d-129">如需詳細資訊，請參閱搭配 [Windows 8 使用虛擬智慧卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。</span><span class="sxs-lookup"><span data-stu-id="4244d-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="4244d-130">設定虛擬智慧卡的 Windows 8</span><span class="sxs-lookup"><span data-stu-id="4244d-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="4244d-131">使用啟用商務用 Skype 之使用者的認證，登入 Windows 8 電腦。</span><span class="sxs-lookup"><span data-stu-id="4244d-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="4244d-132">在 [Windows 8 開始] 畫面上，將游標移至螢幕的右下角。</span><span class="sxs-lookup"><span data-stu-id="4244d-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="4244d-133">選取 [ **搜尋** ] 選項，然後搜尋 forCommand Prompt。</span><span class="sxs-lookup"><span data-stu-id="4244d-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="4244d-134">在 **命令提示** 字元上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="4244d-135">執行下列命令，以 (TPM) 管理主控台開啟受信任的平臺模組：</span><span class="sxs-lookup"><span data-stu-id="4244d-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="4244d-136">在 [TPM 管理主控台] 中，確認您的 TPM 規格版本至少是1。2</span><span class="sxs-lookup"><span data-stu-id="4244d-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="4244d-137">如果您收到的對話方塊指出無法找到相容的信任平臺模組 (TPM) ，請確認該電腦具有相容的 TPM 模組，且已在系統 BIOS 中啟用。</span><span class="sxs-lookup"><span data-stu-id="4244d-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="4244d-138">關閉 TPM 管理主控台</span><span class="sxs-lookup"><span data-stu-id="4244d-138">Close the TPM management console</span></span>

8. <span data-ttu-id="4244d-139">在命令提示字元處，使用下列命令建立新的虛擬智慧卡：</span><span class="sxs-lookup"><span data-stu-id="4244d-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="4244d-140">若要在建立虛擬智慧卡時提供自訂 PIN 碼值，請改用/pin prompt。</span><span class="sxs-lookup"><span data-stu-id="4244d-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="4244d-141">在命令提示字元中執行下列命令，以開啟 [電腦管理] 主控台：</span><span class="sxs-lookup"><span data-stu-id="4244d-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="4244d-142">在 [電腦管理] 主控台中，選取 [ **裝置管理**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="4244d-143">展開 [ **智慧卡讀取器**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="4244d-144">確認已成功建立新的虛擬智慧卡讀取器。</span><span class="sxs-lookup"><span data-stu-id="4244d-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="4244d-145">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="4244d-146">有兩種方法可供您登記智慧卡驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="4244d-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="4244d-147">較簡單的方法是讓使用者直接註冊使用 web 註冊的智慧卡驗證，而更複雜的方法則是使用註冊代理程式。</span><span class="sxs-lookup"><span data-stu-id="4244d-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="4244d-148">本主題著重于智慧卡憑證的自我註冊。</span><span class="sxs-lookup"><span data-stu-id="4244d-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="4244d-149">如需以登錄代理程式名義註冊使用者的詳細資訊，請參閱 [代表其他使用者註冊憑證](https://go.microsoft.com/fwlink/p/?LinkID=313367)。</span><span class="sxs-lookup"><span data-stu-id="4244d-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="4244d-150">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="4244d-151">使用啟用商務用 Skype 之使用者的認證，登入 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="4244d-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="4244d-152">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="4244d-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="4244d-153">流覽至 [ **憑證授權單位 Web 登記** ] 頁面 (https://MyCA.contoso.com/certsrv) 例如，</span><span class="sxs-lookup"><span data-stu-id="4244d-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4244d-154">如果您使用的是 Internet Explorer 10，您可能需要在相容性模式中查看此網站。</span><span class="sxs-lookup"><span data-stu-id="4244d-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="4244d-155">在 [ **歡迎** ] 頁面上，選取 [ **要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="4244d-156">接下來，選取 [ **高級要求**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="4244d-157">選取 [ **建立並提交此 CA 的要求**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="4244d-158">在 [**憑證範本**] 區段中選取 [**智慧卡使用者**]，並以下列值完成「高級憑證要求」：</span><span class="sxs-lookup"><span data-stu-id="4244d-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="4244d-159">**主要選項** 確認他的下列設定：</span><span class="sxs-lookup"><span data-stu-id="4244d-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="4244d-160">選取 [ **建立新的按鍵集** ] 選項按鈕</span><span class="sxs-lookup"><span data-stu-id="4244d-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="4244d-161">若為 **CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]</span><span class="sxs-lookup"><span data-stu-id="4244d-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="4244d-162">如需 **主要用法**，請選取 [ **Exchange** (這是唯一可用的選項) 。</span><span class="sxs-lookup"><span data-stu-id="4244d-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="4244d-163">若為 **金鑰大小**，請輸入2048</span><span class="sxs-lookup"><span data-stu-id="4244d-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="4244d-164">確認已選取 [ **自動機碼容器名稱** ]</span><span class="sxs-lookup"><span data-stu-id="4244d-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="4244d-165">請不要選取其他方塊。</span><span class="sxs-lookup"><span data-stu-id="4244d-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="4244d-166">在 [ **其他選項** ] 下，確認下列值：</span><span class="sxs-lookup"><span data-stu-id="4244d-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="4244d-167">若為 **要求格式** ，請選取 **CMC**。</span><span class="sxs-lookup"><span data-stu-id="4244d-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="4244d-168">若為 **雜湊演算法** ，請選取 **sha1**。</span><span class="sxs-lookup"><span data-stu-id="4244d-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="4244d-169">適用于 **易記名稱** enterSmardcard 憑證。</span><span class="sxs-lookup"><span data-stu-id="4244d-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="4244d-170">如果您使用的是實體智慧卡讀卡機，請將智慧卡插入裝置中。</span><span class="sxs-lookup"><span data-stu-id="4244d-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="4244d-171">按一下 [ **提交** ] 提交憑證要求。</span><span class="sxs-lookup"><span data-stu-id="4244d-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="4244d-172">出現提示時，請輸入用來建立虛擬智慧卡的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="4244d-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4244d-173">預設虛擬智慧卡 PIN 碼值為 ' 12345678 '。</span><span class="sxs-lookup"><span data-stu-id="4244d-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="4244d-174">簽發憑證後，按一下 [ **安裝此憑證** ] 以完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="4244d-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4244d-175">如果憑證要求失敗，錯誤為「此網頁瀏覽器不支援產生憑證要求」，有三種方法可以解決問題：</span><span class="sxs-lookup"><span data-stu-id="4244d-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="4244d-176">設定 Active Directory Federation Services (AD FS 2.0) </span><span class="sxs-lookup"><span data-stu-id="4244d-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="4244d-177">下列章節說明如何設定 Active Directory Federation Services (AD FS 2.0) 以支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="4244d-178">如需如何安裝 AD FS 2.0 的詳細資訊，請參閱 [AD fs 2.0 逐步和操作方法指南](https://go.microsoft.com/fwlink/p/?LinkId=313374)。</span><span class="sxs-lookup"><span data-stu-id="4244d-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="4244d-179">安裝 AD FS 2.0 時，請勿使用 Windows Server 管理員來新增 Active Directory Federation Services 角色。</span><span class="sxs-lookup"><span data-stu-id="4244d-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="4244d-180">相反地，請下載並安裝 [Active Directory Federation Services 2.0 幫手 rtw 套件](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="4244d-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="4244d-181">設定用於雙因素驗證的 AD FS</span><span class="sxs-lookup"><span data-stu-id="4244d-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="4244d-182">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="4244d-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="4244d-183">啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4244d-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="4244d-184">在 [Windows PowerShell] 命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4244d-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="4244d-185">執行下列命令，以建立與每一部要啟用被動驗證的伺服器的合作關係，以取代您的部署特有的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="4244d-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="4244d-186">在 [系統管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="4244d-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="4244d-187">展開 [**信任關係**  >  **信賴** 憑證者信任]。</span><span class="sxs-lookup"><span data-stu-id="4244d-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="4244d-188">確認已為您的商務用 Skype Server 建立新的信任。</span><span class="sxs-lookup"><span data-stu-id="4244d-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="4244d-189">執行下列命令，為使用 Windows PowerShell 的信賴憑證者信任建立並指派發行授權規則：</span><span class="sxs-lookup"><span data-stu-id="4244d-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="4244d-190">執行下列命令，為您使用 Windows PowerShell 建立並指派「信賴憑證方信任」的發行轉換規則：</span><span class="sxs-lookup"><span data-stu-id="4244d-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="4244d-191">在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下您的信賴憑證者信任，然後選取 [ **編輯宣告規則**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="4244d-192">選取 [ **發行授權規則** ] 索引標籤，並確認已成功建立新的授權規則。</span><span class="sxs-lookup"><span data-stu-id="4244d-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="4244d-193">選取 [ **發行轉換規則** ] 索引標籤，並確認已成功建立新的轉換規則。</span><span class="sxs-lookup"><span data-stu-id="4244d-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="4244d-194">設定 AD FS 2.0 以支援用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="4244d-195">有兩種可能的驗證類型可設定為允許 AD FS 2.0 支援使用智慧卡的驗證：</span><span class="sxs-lookup"><span data-stu-id="4244d-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="4244d-196">以表單為基礎的驗證 (FBA) </span><span class="sxs-lookup"><span data-stu-id="4244d-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="4244d-197">傳輸層安全性用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="4244d-198">使用以表單為基礎的驗證，您可以開發一個網頁，讓使用者可以使用其使用者名稱/密碼或使用智慧卡和 PIN 碼進行驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="4244d-199">本主題著重于如何使用 AD FS 2.0 來執行傳輸層安全性用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="4244d-200">如需 AD FS 2.0 驗證類型的相關資訊，請參閱 [AD fs 2.0：如何變更本機驗證類型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。</span><span class="sxs-lookup"><span data-stu-id="4244d-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="4244d-201">設定 AD FS 2.0 以支援用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="4244d-202">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="4244d-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="4244d-203">啟動 Windows Explorer。</span><span class="sxs-lookup"><span data-stu-id="4244d-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="4244d-204">流覽至 C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="4244d-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="4244d-205">請備份現有的 web.config 檔。</span><span class="sxs-lookup"><span data-stu-id="4244d-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="4244d-206">使用 [記事本] 開啟現有的 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="4244d-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="4244d-207">從功能表列中，選取 [ **編輯** ]，然後選取 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="4244d-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="4244d-208">搜尋 \<localAuthenticationTypes\> 。</span><span class="sxs-lookup"><span data-stu-id="4244d-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="4244d-209">請注意，列出了四種驗證類型，每行一個。</span><span class="sxs-lookup"><span data-stu-id="4244d-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="4244d-210">將包含 TLSClient 驗證類型的行移至區段中清單的頂端。</span><span class="sxs-lookup"><span data-stu-id="4244d-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="4244d-211">儲存並關閉 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="4244d-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="4244d-212">以較高的許可權啟動命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="4244d-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="4244d-213">執行下列命令以重新啟動 IIS：</span><span class="sxs-lookup"><span data-stu-id="4244d-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="4244d-214">設定商務用 Skype Server 被動式驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="4244d-215">下列章節說明如何設定商務用 Skype 伺服器以支援被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="4244d-216">一旦啟用，啟用兩個要素驗證的使用者將需要使用實體或虛擬智慧卡和有效 PIN 碼以商務用 Skype 用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="4244d-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="4244d-217">強烈建議客戶在服務層級為註冊機構和 Web 服務啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="4244d-218">如果已為全域層級的註冊機構和 Web 服務啟用被動式驗證，則對於不是以支援的桌面用戶端登入的使用者而言，這可能會導致組織範圍的驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="4244d-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="4244d-219">Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="4244d-219">Web Service Configuration</span></span>

<span data-ttu-id="4244d-220">下列步驟說明如何針對 Director、Enterprise Pool 和 Standard Edition server 建立自訂 web 服務設定，以進行被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="4244d-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="4244d-221">建立自訂 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="4244d-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="4244d-222">使用商務用 Skype 系統管理員帳戶登入商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="4244d-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="4244d-223">啟動商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="4244d-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="4244d-224">從商務用 Skype Server 管理命令介面命令列，針對每個 Director、Enterprise 集區和 Standard Edition Server 建立新的 Web 服務設定，並執行下列命令，以啟用被動驗證：</span><span class="sxs-lookup"><span data-stu-id="4244d-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="4244d-225">WsFedPassiveMetadataUri FQDN 的值為 AD FS 2.0 伺服器的同盟服務名稱。</span><span class="sxs-lookup"><span data-stu-id="4244d-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="4244d-226">您可以在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下功能窗格中的 [ **服務** ]，然後選取 [ **編輯同盟服務屬性**]，即可找到 [同盟服務名稱] 值。</span><span class="sxs-lookup"><span data-stu-id="4244d-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="4244d-227">執行下列命令，確認 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值已正確設定：</span><span class="sxs-lookup"><span data-stu-id="4244d-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="4244d-228">若為用戶端，被動式驗證是 webticket 驗證的最低偏好驗證方法。</span><span class="sxs-lookup"><span data-stu-id="4244d-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="4244d-229">針對將為進行被動式驗證而啟用的所有 Director、Enterprise Pool 和 Standard Edition server，您必須在商務用 Skype Web 服務中使用下列 Cmdlet 來停用所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="4244d-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="4244d-230">執行下列 Cmdlet，確認已成功停用所有其他驗證類型：</span><span class="sxs-lookup"><span data-stu-id="4244d-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="4244d-231">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="4244d-231">Proxy Configuration</span></span>

<span data-ttu-id="4244d-232">為商務用 Skype Web 服務停用憑證驗證時，商務用 Skype 用戶端將使用較不習慣的驗證類型，例如 Kerberos 或 NTLM，以驗證註冊機構服務。</span><span class="sxs-lookup"><span data-stu-id="4244d-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="4244d-233">仍然需要使用憑證驗證，讓用戶端可以找回 webticket，但必須停用註冊器服務的 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="4244d-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="4244d-234">下列步驟說明如何針對將啟用被動驗證的 Edge 集區、Enterprise 集區和 Standard Edition server 建立自訂 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="4244d-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="4244d-235">建立自訂 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="4244d-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="4244d-236">從商務用 Skype Server 管理命令介面命令列，針對每個商務用 Skype Server Edge 集區、Enterprise 集區和 Standard Edition server 建立新的 proxy 設定，並執行下列命令來啟用被動驗證：</span><span class="sxs-lookup"><span data-stu-id="4244d-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="4244d-237">執行下列命令，確認已成功停用所有其他 proxy 驗證類型：</span><span class="sxs-lookup"><span data-stu-id="4244d-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="4244d-238">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4244d-238">See also</span></span>

[<span data-ttu-id="4244d-239">在商務用 Skype Server 中管理雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="4244d-240">搭配商務用 Skype 用戶端和商務用 Skype Server 使用雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="4244d-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)

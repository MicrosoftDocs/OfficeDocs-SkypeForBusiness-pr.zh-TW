---
title: 允許使用者連絡外部商務用 Skype 使用者
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '瞭解如何設定商務用 Skype，讓使用者與另一個組織的使用者交談，或讓外部連絡人與使用者交談。 '
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093507"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="fcdf4-103">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="fcdf4-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="fcdf4-104">在下列時間使用本文中的步驟：</span><span class="sxs-lookup"><span data-stu-id="fcdf4-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="fcdf4-105">您擁有公司中不同網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-105">You have users on different domains in your business.</span></span> <span data-ttu-id="fcdf4-106">例如，Rob@ContosoEast.com Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="fcdf4-107">您希望貴組織的人員使用商務用 Skype 與組織外部特定企業的人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="fcdf4-108">您希望世界上任何使用商務用 Skype 的人，都能使用您的電子郵件地址尋找並與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="fcdf4-109">如果您和他們都使用預設的商務用 Skype 設定，這會自動執行。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="fcdf4-110">如果沒有，則他們必須確定其組塊未封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="fcdf4-111">為使用者啟用企業對商務通訊</span><span class="sxs-lookup"><span data-stu-id="fcdf4-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="fcdf4-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="fcdf4-113">您必須同時 [擁有](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Microsoft 365 或 Office 365 的系統管理員許可權，才能進行此通訊。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="fcdf4-114">![顯示 Microsoft Teams 標誌的圖示 ](../images/teams-logo-30x30.png) **使用 Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="fcdf4-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="fcdf4-115">使用 Microsoft 365 或 Office 365 系統管理員帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="fcdf4-116">在系統管理中心，前往 **系統管理中心**  >  **Teams**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![選擇 Teams 系統管理員。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="fcdf4-118">在 **Teams 中心，** 選擇 **Skype** > **舊版入口網站** 
  ![ 選擇 SfB 舊版入口網站。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="fcdf4-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="fcdf4-119">在 [商務用 Skype 系統管理中心]，選擇 [組織]  >  [外部通訊]。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="fcdf4-120">若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="fcdf4-121">或者，如果您想要啟用與已開啟商務用 Skype 政策之全球其他所有人的通訊，請選擇開啟 ，但封鎖的 **網域除外**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="fcdf4-122">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-122">This is the default setting.</span></span>

6. <span data-ttu-id="fcdf4-123">在 **封鎖或允許的網域** 下，選擇並新增您想要 **+** 允許的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="fcdf4-124">請確定另一組織的系統管理員在商務用 Skype 系統管理中心 **執行這些步驟**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="fcdf4-125">例如，在允許 **的網域** 清單中，他們的系統管理員必須輸入您企業所需的網域。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="fcdf4-126">如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="fcdf4-127">如果貴組織使用不同的防火牆解決方案來限制網路上的電腦無法連接到網際網路，請確保您的用戶端電腦能夠存取下列 [Office 365 URL](/microsoftteams/office-365-urls-ip-address-ranges)和 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="fcdf4-128">這可能需要將 FQDNs 新增到防火牆或 Proxy 基礎結構組配置的外發允許清單 **\* ：.api.skype.com、.users.storage.live.com** \* *__\*\*\*和 graph.skype.com。*\*</span><span class="sxs-lookup"><span data-stu-id="fcdf4-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="fcdf4-129">若要瞭解如何在防火牆中開啟這些埠的指示，請查看它所提供的檔。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="fcdf4-130">有關您需要開啟的所有埠清單，請參閱 [Office 365 URL 和 IP 位址範圍](/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="fcdf4-131">請確定組織的系統管理員也遵循這些步驟。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="fcdf4-132">**等候最多 24 小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="fcdf4-133">當您變更外部通訊設定時，變更最多可能需要 24 小時，才能填入所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="fcdf4-134">![Skype：您可以允許使用者與使用免費消費者應用程式 Skype 的每個人一起搜尋和 ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) IM！</span><span class="sxs-lookup"><span data-stu-id="fcdf4-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="fcdf4-135">若要深入瞭解，請參閱 [讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="fcdf4-136">測試和疑難排解</span><span class="sxs-lookup"><span data-stu-id="fcdf4-136">Test and troubleshoot</span></span>

<span data-ttu-id="fcdf4-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="fcdf4-138">**在設定企業間通訊時，最常見的問題是正確取得 [Office 365 URL](/microsoftteams/office-365-urls-ip-address-ranges) 和 IP 位址範圍。**</span><span class="sxs-lookup"><span data-stu-id="fcdf4-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="fcdf4-139">若要測試您的設定，您需要不在公司防火牆後面的商務用 Skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="fcdf4-140">變更外部通訊設定之後，請等候 **最多 24 小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="fcdf4-141">在商務用 Skype 中，在商務用 Skype 中搜尋您的連絡人，然後傳送聊天要求。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="fcdf4-142">如果您收到由於公司政策無法送出的郵件，您必須仔細檢查 [您的 Office 365 URL](/microsoftteams/office-365-urls-ip-address-ranges)和 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="fcdf4-143">要求商務用 Skype 連絡人傳送聊天邀請。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="fcdf4-144">如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="fcdf4-145">另一個測試問題是否出在防火牆上的方法，就是前往防火牆後面的 Wifi 位置，例如咖啡店。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="fcdf4-146">使用商務用 Skype 傳送要求給聯絡人聊天。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="fcdf4-147">如果郵件經過該區，但在您工作時卻無法傳遞，那麼您就會知道問題出在防火牆上。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="fcdf4-148">如何尋找其他人，以及如何在與另一個企業聯繫時找到他們</span><span class="sxs-lookup"><span data-stu-id="fcdf4-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="fcdf4-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="fcdf4-150">啟用與其他商務用 Skype 使用者的外部通訊後，您的使用者可以搜尋其登錄名稱來尋找聯合商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="fcdf4-151">例如，Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="fcdf4-152">接著，他們將需要將人員新增到連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-152">Then they will need to add the person to their list of contacts.</span></span>
  
![若要在聯合企業中尋找使用者，您必須搜尋其電子郵件地址 (這通常也是他們) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="fcdf4-154">設定與聯盟企業通訊的秘訣</span><span class="sxs-lookup"><span data-stu-id="fcdf4-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="fcdf4-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="fcdf4-156">若要設定商務用 Skype 2015 與商務用 Skype Online 之間的聯合，請參閱這篇文章：設定商務用 [Skype Online 的](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)聯盟。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="fcdf4-157">若要設定 Lync 與商務用 Skype Online 之間的聯合，請參閱這篇文章：設定 Lync Online 客戶的 [聯盟支援](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="fcdf4-158">當 Microsoft 365 或 Office 365 中的兩個商務用 Skype 使用者正在個別網域上彼此通訊時，他們只能使用商務用 Skype 功能 (例如，在兩個組織開啟的視像交談或桌面共用) 。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="fcdf4-159">如果貴組織的商務用 Skype 使用者被置於 In-Place 或訴訟保留，該使用者與其他商務用 Skype 或 Skype 使用者之間的任何 IM 交談都會儲存于其信箱中的可復原專案中。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="fcdf4-160">這些交談不會儲存于信箱中的交談記錄資料夾中。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="fcdf4-161">關閉特定人員的外部通訊</span><span class="sxs-lookup"><span data-stu-id="fcdf4-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="fcdf4-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="fcdf4-163">啟用整個企業的外部通訊之後，您可以只針對特定人員關閉外部通訊。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="fcdf4-164">使用 Microsoft 365 或 Office 365 系統管理員帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="fcdf4-165">在系統管理中心，前往使用者  >  **活動使用者**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="fcdf4-166">在使用者清單中，選擇使用者，然後在 [其他設定> **下，按一下** **[編輯商務用 Skype 屬性**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![選擇商務用 Skype](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="fcdf4-168">在商務 **用 Skype 系統管理中心**，選擇 **外部通訊**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="fcdf4-169">在選項 **頁面上** ，會選取所有選項。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="fcdf4-170">清除您想要停用的通訊。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="fcdf4-171">下圖顯示 Jakob 將能夠與其他信任企業的人員通訊，但無法與其他 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![選擇外部連絡人](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="fcdf4-173">選擇 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="fcdf4-174">您可能必須等候最多 24 小時，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="fcdf4-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="fcdf4-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="fcdf4-175">Related topics</span></span>

<span data-ttu-id="fcdf4-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="fcdf4-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="fcdf4-177">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="fcdf4-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="fcdf4-178">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="fcdf4-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

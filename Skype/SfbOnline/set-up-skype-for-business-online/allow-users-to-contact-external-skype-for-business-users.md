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
description: '瞭解如何設定商務用 Skype，讓使用者與其他組織中的使用者交談，或讓連絡人與他人交談。 '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625049"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="02c3c-103">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="02c3c-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="02c3c-104">在下列情況下，請使用本文中的步驟：</span><span class="sxs-lookup"><span data-stu-id="02c3c-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="02c3c-105">您的企業中有不同網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="02c3c-105">You have users on different domains in your business.</span></span> <span data-ttu-id="02c3c-106">例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="02c3c-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="02c3c-107">您希望貴組織中的人員可以使用商務用 Skype 與組織外部的特定企業中的人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="02c3c-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="02c3c-108">您希望世界各地的其他人都能使用商務用 Skype，透過您的電子郵件地址找出並與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="02c3c-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="02c3c-109">如果您與他們使用預設的商務用 Skype 設定，這將會自動運作。</span><span class="sxs-lookup"><span data-stu-id="02c3c-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="02c3c-110">如果不是，則必須確認他們的設定不會封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="02c3c-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="02c3c-111">為使用者啟用企業對企業通訊</span><span class="sxs-lookup"><span data-stu-id="02c3c-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="02c3c-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="02c3c-113">您必須在兩家組織的 Microsoft 365 或 Office 365 中擁有系統 [管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ，才能進行這項通訊。</span><span class="sxs-lookup"><span data-stu-id="02c3c-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="02c3c-114">![](../images/teams-logo-30x30.png)**使用 [團隊管理中心**] 顯示 Microsoft 小組標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="02c3c-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="02c3c-115">使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="02c3c-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="02c3c-116">在系統管理中心中，移至 [系統**管理中心**]  >  **小組**。</span><span class="sxs-lookup"><span data-stu-id="02c3c-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![選擇 [團隊管理員]。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="02c3c-118">在 [**小組中心**] 中，選擇 [ **Skype** > **傳統版入口網站**] 
  ![ 選擇 [SfB 舊版入口網站]。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="02c3c-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="02c3c-119">在 [商務用 Skype 系統管理中心]\*\*\*\*，選擇 [組織]\*\*\*\*  >  [外部通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02c3c-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="02c3c-120">若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02c3c-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="02c3c-121">或者，如果您想要與世界各地擁有開啟商務用 Skype 原則的其他人通訊，請選擇 [ **除了封鎖的網域以外**]。</span><span class="sxs-lookup"><span data-stu-id="02c3c-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="02c3c-122">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="02c3c-122">This is the default setting.</span></span>

6. <span data-ttu-id="02c3c-123">在 [ **封鎖或允許的網域**] 下，選擇 **+** 並新增您要允許的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="02c3c-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="02c3c-124">確定其他組織中的系統管理員在 **商務用 Skype 系統管理中心**執行這些相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="02c3c-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="02c3c-125">例如，在他們的 [ **允許的網域** ] 清單中，他們的管理員必須為您的企業輸入網域。</span><span class="sxs-lookup"><span data-stu-id="02c3c-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="02c3c-126">如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="02c3c-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="02c3c-127">如果您的組織使用不同的防火牆解決方案來限制您網路上的電腦連線至網際網路，請確定您的用戶端電腦能夠存取下列 [Office 365 url 和 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="02c3c-128">這可能需要在防火牆或 proxy 基礎結構設定： \*\* \* . api.skype.com**、 \* **users.storage.live.com**和**graph.skype.com\*\*中，將 fqdn 新增到輸出允許清單中。</span><span class="sxs-lookup"><span data-stu-id="02c3c-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="02c3c-129">如需如何在防火牆中開啟這些埠的相關指示，請參閱它隨附的檔。</span><span class="sxs-lookup"><span data-stu-id="02c3c-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="02c3c-130">如需開啟所有埠的清單，請參閱 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="02c3c-131">請確定組織中的系統管理員也已遵循這些步驟。</span><span class="sxs-lookup"><span data-stu-id="02c3c-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="02c3c-132">請**等候長達24小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="02c3c-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="02c3c-133">當您變更 [外部通訊] 設定時，最多可能需要24小時的時間，才能在所有資料中心上填入這些變更。</span><span class="sxs-lookup"><span data-stu-id="02c3c-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="02c3c-134">![Skype ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 您可以讓使用者在使用 Skype 的所有人（免費消費者 app）中搜尋和傳送即時消息！</span><span class="sxs-lookup"><span data-stu-id="02c3c-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="02c3c-135">若要深入瞭解，請參閱 [讓商務用 Skype 使用者新增 skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="02c3c-136">測試和疑難排解</span><span class="sxs-lookup"><span data-stu-id="02c3c-136">Test and troubleshoot</span></span>

<span data-ttu-id="02c3c-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="02c3c-138">**當您設定企業對企業通訊時，最常遇到的問題就是將其 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) 直接取得正確。**</span><span class="sxs-lookup"><span data-stu-id="02c3c-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="02c3c-139">若要測試您的設定，您需要不在公司防火牆後的商務用 Skype 的連絡人。</span><span class="sxs-lookup"><span data-stu-id="02c3c-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="02c3c-140">在您變更 [外部通訊] 設定之後，請 **等候長達24小時以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="02c3c-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="02c3c-141">在商務用 Skype 中，在商務用 Skype 中搜尋您的連絡人，然後傳送要求到聊天。</span><span class="sxs-lookup"><span data-stu-id="02c3c-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="02c3c-142">如果您收到因公司原則無法傳送的訊息，您必須仔細檢查您的 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="02c3c-143">要求您的商務用 Skype 連絡人向您傳送聊天的要求。</span><span class="sxs-lookup"><span data-stu-id="02c3c-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="02c3c-144">如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="02c3c-145">測試問題是否為您防火牆的另一種方法，就是移至不在防火牆背後的 wifi 位置（例如咖啡廳）。</span><span class="sxs-lookup"><span data-stu-id="02c3c-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="02c3c-146">使用商務用 Skype 將要求傳送給您的連絡人以進行交談。</span><span class="sxs-lookup"><span data-stu-id="02c3c-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="02c3c-147">如果郵件在其中，但不在您的工作中，您知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="02c3c-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="02c3c-148">如何在與其他公司連線時找到其他人並找到其他人</span><span class="sxs-lookup"><span data-stu-id="02c3c-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="02c3c-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="02c3c-150">在您啟用與其他商務用 Skype 使用者的外部通訊之後，您的使用者就可以搜尋其登入名稱，找到聯盟的商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="02c3c-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="02c3c-151">Rob@contoso.com 就是一個範例。</span><span class="sxs-lookup"><span data-stu-id="02c3c-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="02c3c-152">接著他們將需要將人員新增至他們的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="02c3c-152">Then they will need to add the person to their list of contacts.</span></span>
  
![若要尋找同盟企業中的使用者，您必須搜尋其電子郵件地址 (通常也是他們的登入名稱) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="02c3c-154">設定與同盟企業通訊的秘訣</span><span class="sxs-lookup"><span data-stu-id="02c3c-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="02c3c-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="02c3c-156">若要在商務用 Skype 2015 與商務用 Skype Online 之間設定同盟，請參閱這篇文章： [使用商務用 Skype Online 設定同盟](https://technet.microsoft.com/library/jj205126.aspx)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="02c3c-157">若要在 Lync 與商務用 Skype Online 之間設定同盟，請參閱這篇文章：為 [Lync Online 客戶設定同盟支援](https://technet.microsoft.com/library/hh202193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="02c3c-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="02c3c-158">當 Microsoft 365 或 Office 365 中的兩個商務用 Skype 使用者彼此通訊于不同的網域時，他們只能使用商務用 Skype 功能 (例如，在兩個組織中開啟的影片交談或桌面共用) 。</span><span class="sxs-lookup"><span data-stu-id="02c3c-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="02c3c-159">如果貴組織中的商務用 Skype 使用者已加入 In-Place 或訴訟封存，該使用者與其他商務用 Skype 或 Skype 使用者之間的任何 IM 交談，都會儲存在其信箱中的 **可復原專案** 中。</span><span class="sxs-lookup"><span data-stu-id="02c3c-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="02c3c-160">這些交談不會儲存在其信箱中的 [ **交談記錄** ] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02c3c-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="02c3c-161">關閉特定人員的外部通訊</span><span class="sxs-lookup"><span data-stu-id="02c3c-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="02c3c-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="02c3c-163">在您為整個企業啟用外部溝通之後，您就可以針對特定的人員關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="02c3c-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="02c3c-164">使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="02c3c-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="02c3c-165">在系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="02c3c-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="02c3c-166">在使用者清單中，選擇使用者，然後在 [ **其他設定**] 底下，按一下 [ **編輯商務用 Skype 屬性**]。</span><span class="sxs-lookup"><span data-stu-id="02c3c-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![選擇商務用 Skype](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="02c3c-168">在 **商務用 Skype 系統管理中心**中，選擇 [ **外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="02c3c-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="02c3c-169">在 [ **選項** ] 頁面上，將會選取所有選項。</span><span class="sxs-lookup"><span data-stu-id="02c3c-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="02c3c-170">清除您想要停用的通訊。</span><span class="sxs-lookup"><span data-stu-id="02c3c-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="02c3c-171">下列影像顯示 Jakob 將能夠與其他信任的公司中的人員通訊，但無法與其他 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="02c3c-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![選擇外部連絡人](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="02c3c-173">選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="02c3c-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="02c3c-174">您可能需要等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="02c3c-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="02c3c-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="02c3c-175">Related topics</span></span>

<span data-ttu-id="02c3c-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="02c3c-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="02c3c-177">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="02c3c-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="02c3c-178">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="02c3c-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
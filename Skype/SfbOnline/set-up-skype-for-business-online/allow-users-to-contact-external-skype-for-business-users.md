---
title: 允許使用者與外部商務用 Skype 使用者聯繫
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
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: '瞭解如何設定商務用 Skype，讓使用者與其他組織中的使用者交談，或讓連絡人以外的人員。 '
ms.openlocfilehash: 570861f532371dc8eca253956ffdd200e60f5990
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642439"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="dfea0-103">允許使用者與外部商務用 Skype 使用者聯繫</span><span class="sxs-lookup"><span data-stu-id="dfea0-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="dfea0-104">商務用 Skype 同盟不適用於由世紀運營的 Office 365 和 Office 365 德國組織。</span><span class="sxs-lookup"><span data-stu-id="dfea0-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="dfea0-105">在下列情況下，請使用本文中的步驟：</span><span class="sxs-lookup"><span data-stu-id="dfea0-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="dfea0-106">您的企業中有不同網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="dfea0-106">You have users on different domains in your business.</span></span> <span data-ttu-id="dfea0-107">例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="dfea0-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="dfea0-108">您希望貴組織中的人員可以使用商務用 Skype 與組織外部的特定企業中的人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="dfea0-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="dfea0-109">您希望世界各地的其他人都能使用商務用 Skype，透過您的電子郵件地址找出並與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="dfea0-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="dfea0-110">如果您與他們使用預設的商務用 Skype 設定，這將會自動運作。</span><span class="sxs-lookup"><span data-stu-id="dfea0-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="dfea0-111">如果不是，則必須確認他們的設定不會封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="dfea0-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="dfea0-112">為使用者啟用企業對企業通訊</span><span class="sxs-lookup"><span data-stu-id="dfea0-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="dfea0-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-113"></span></span>

<span data-ttu-id="dfea0-114">您必須在兩個組織的 Office 365 中擁有系統[管理員許可權](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="dfea0-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="dfea0-115">![](../images/teams-logo-30x30.png) **使用 [團隊管理中心**] 顯示 Microsoft 小組標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="dfea0-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="dfea0-116">使用您的 Office 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dfea0-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="dfea0-117">在系統管理中心中，移至 [系統**管理中心** > ]**小組**。</span><span class="sxs-lookup"><span data-stu-id="dfea0-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![選擇 [團隊管理員]。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="dfea0-119">在 [**小組中心**] 中，選擇 [ **Skype** > **傳統版入口網站** 
 ![] 選擇 [SfB 舊版入口網站]。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="dfea0-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="dfea0-120">在**商務用 Skype 系統管理中心**中，選擇 [**組織** > **外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="dfea0-121">若要設定與特定企業或其他網域中的使用者通訊，請在下拉式方塊中，選擇 [**只對允許的網域開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="dfea0-122">或者，如果您想要與世界各地擁有開啟商務用 Skype 原則的其他人通訊，請選擇 [**除了封鎖的網域以外**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="dfea0-123">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="dfea0-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="dfea0-124">在 [**封鎖或允許**的網域**+** ] 下，選擇並新增您要允許的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="dfea0-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="dfea0-125">確定其他組織中的系統管理員在**商務用 Skype 系統管理中心**執行這些相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="dfea0-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="dfea0-126">例如，在他們的 [**允許的網域**] 清單中，他們的管理員必須為您的企業輸入網域。</span><span class="sxs-lookup"><span data-stu-id="dfea0-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="dfea0-127">如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="dfea0-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="dfea0-128">如果您的組織使用不同的防火牆解決方案來限制您網路上的電腦連線至網際網路，請確定您的用戶端電腦能夠存取下列[Office 365 url 和 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="dfea0-129">這可能需要在防火牆或 proxy 基礎結構設定： \*\* \*. api.skype.com**、 \* **users.storage.live.com**和**graph.skype.com\*\*中，將 fqdn 新增到輸出允許清單中。</span><span class="sxs-lookup"><span data-stu-id="dfea0-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="dfea0-130">如需如何在防火牆中開啟這些埠的相關指示，請參閱它隨附的檔。</span><span class="sxs-lookup"><span data-stu-id="dfea0-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="dfea0-131">如需開啟所有埠的清單，請參閱[Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="dfea0-132">請確定組織中的系統管理員也已遵循這些步驟。</span><span class="sxs-lookup"><span data-stu-id="dfea0-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="dfea0-133">請**等候長達24小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="dfea0-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="dfea0-134">每當您變更 [外部通訊] 設定時，最多可能需要24小時才能在所有資料中心上填入變更。</span><span class="sxs-lookup"><span data-stu-id="dfea0-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="dfea0-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)您可以讓使用者在使用 Skype 的所有人（免費消費者 app）中搜尋和傳送即時消息！</span><span class="sxs-lookup"><span data-stu-id="dfea0-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="dfea0-136">若要深入瞭解，請參閱[讓商務用 Skype 使用者新增 skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="dfea0-137">測試和疑難排解</span><span class="sxs-lookup"><span data-stu-id="dfea0-137">Test and troubleshoot</span></span>
<span data-ttu-id="dfea0-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-138"></span></span>

 <span data-ttu-id="dfea0-139">**當您設定企業對企業通訊時，最常遇到的問題就是將其[Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)直接取得正確。**</span><span class="sxs-lookup"><span data-stu-id="dfea0-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="dfea0-140">若要測試您的設定，您需要不在公司防火牆後的商務用 Skype 的連絡人。</span><span class="sxs-lookup"><span data-stu-id="dfea0-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="dfea0-141">在您變更 [外部通訊] 設定之後，請**等候長達24小時以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="dfea0-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="dfea0-142">在商務用 Skype 中，在商務用 Skype 中搜尋您的連絡人，然後傳送要求到聊天。</span><span class="sxs-lookup"><span data-stu-id="dfea0-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="dfea0-143">如果您收到因公司原則無法傳送的訊息，您必須仔細檢查您的[Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="dfea0-144">要求您的商務用 Skype 連絡人向您傳送聊天的要求。</span><span class="sxs-lookup"><span data-stu-id="dfea0-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="dfea0-145">如果您沒有收到他們的要求，問題就是您的防火牆設定（假設他們已確認其防火牆設定正確）。</span><span class="sxs-lookup"><span data-stu-id="dfea0-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="dfea0-146">測試問題是否是您的防火牆的另一種方法是，移至不在防火牆背後（例如咖啡廳）的 wifi 位置，然後使用商務用 Skype 將要求傳送給您的連絡人進行聊天。</span><span class="sxs-lookup"><span data-stu-id="dfea0-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="dfea0-147">如果郵件在其中，但不在您的工作中，您知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="dfea0-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="dfea0-148">如何在與其他公司連線時找到其他人並找到其他人</span><span class="sxs-lookup"><span data-stu-id="dfea0-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="dfea0-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-149"></span></span>

<span data-ttu-id="dfea0-150">在您啟用與其他商務用 Skype 使用者的外部通訊之後，您的使用者就可以搜尋其登入名稱，以找到商務用 Skype 使用者：例如 Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dfea0-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="dfea0-151">接著他們將需要將人員新增至他們的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="dfea0-151">Then they will need to add the person to their list of contacts.</span></span>
  
![若要尋找同盟企業中的使用者，您必須搜尋其電子郵件地址（通常也是他們的登入名稱）。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="dfea0-153">設定與同盟企業通訊的秘訣</span><span class="sxs-lookup"><span data-stu-id="dfea0-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="dfea0-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-154"></span></span>

- <span data-ttu-id="dfea0-155">若要在商務用 Skype 2015 與商務用 Skype Online 之間設定同盟，請參閱這篇文章：[使用商務用 Skype Online 設定同盟](https://technet.microsoft.com/en-us/library/jj205126.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="dfea0-156">若要在 Lync 與商務用 Skype Online 之間設定同盟，請參閱這篇文章：為[Lync Online 客戶設定同盟支援](https://technet.microsoft.com/en-us/library/hh202193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dfea0-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="dfea0-157">當 Office 365 中的兩個商務用 Skype 使用者互相通訊在不同的網域上時，他們只能使用在兩個組織中開啟的商務用 Skype 功能（例如，影片交談或桌面共用）。</span><span class="sxs-lookup"><span data-stu-id="dfea0-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="dfea0-158">如果貴組織中的商務用 Skype 使用者已加入就地或訴訟封存，該使用者與其他商務用 Skype 或 Skype 使用者之間的任何 IM 交談，都會儲存在其信箱中的**可復原專案**中。</span><span class="sxs-lookup"><span data-stu-id="dfea0-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="dfea0-159">這些交談不會儲存在其信箱中的 [**交談記錄**] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="dfea0-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="dfea0-160">關閉特定人員的外部通訊</span><span class="sxs-lookup"><span data-stu-id="dfea0-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="dfea0-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-161"></span></span>

<span data-ttu-id="dfea0-162">在您為整個企業啟用外部溝通之後，您就可以針對特定的人員關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="dfea0-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="dfea0-163">使用您的 Office 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dfea0-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="dfea0-164">在系統管理中心中，移至 [**使用者** > 作用中的**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="dfea0-165">在使用者清單中，選擇使用者，然後在 [**其他設定**] 底下，按一下 [**編輯商務用 Skype 屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![選擇商務用 Skype](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="dfea0-167">在**商務用 Skype 系統管理中心**中，選擇 [**外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="dfea0-168">在 [**選項**] 頁面上，將會選取所有選項。</span><span class="sxs-lookup"><span data-stu-id="dfea0-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="dfea0-169">清除您想要停用的通訊。</span><span class="sxs-lookup"><span data-stu-id="dfea0-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="dfea0-170">下列影像顯示 Jakob 將能夠與其他信任的公司中的人員通訊，但無法與其他 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="dfea0-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![選擇外部連絡人](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="dfea0-172">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dfea0-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dfea0-173">您可能需要等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="dfea0-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="dfea0-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="dfea0-174">Related topics</span></span>
<span data-ttu-id="dfea0-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="dfea0-175"></span></span>

[<span data-ttu-id="dfea0-176">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="dfea0-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="dfea0-177">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="dfea0-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 

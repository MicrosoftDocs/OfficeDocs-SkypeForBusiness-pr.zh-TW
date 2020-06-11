---
title: 變更問候語和電子郵件的預設語言
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 瞭解如何設定商務用 Skype 針對貴組織的預設語音信箱問候語使用另一種語言。
ms.openlocfilehash: 988f09141913c72b9334b28d2c218b15bdbf3376
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691389"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="74bf6-103">變更問候語和電子郵件的預設語言</span><span class="sxs-lookup"><span data-stu-id="74bf6-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="74bf6-104">如果您是[全域系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，您可以設定商務用 Skype，以另一種語言播放預設的語音信箱問候語。</span><span class="sxs-lookup"><span data-stu-id="74bf6-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="74bf6-105">預設的系統問候語就像「請留言給張三張。</span><span class="sxs-lookup"><span data-stu-id="74bf6-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="74bf6-106">音調之後，請錄製您的訊息。</span><span class="sxs-lookup"><span data-stu-id="74bf6-106">After the tone, please record your message.</span></span> <span data-ttu-id="74bf6-107">錄製完畢後，請掛斷，或按井井號鍵以取得更多選項。</span><span class="sxs-lookup"><span data-stu-id="74bf6-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="74bf6-108">**首先，請閱讀下列重要資訊：**</span><span class="sxs-lookup"><span data-stu-id="74bf6-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="74bf6-109">**您可使用的語言是由貴組織的位置決定**。</span><span class="sxs-lookup"><span data-stu-id="74bf6-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="74bf6-110">例如，如果您的組織位於美國，您可以將預設語言設定為英文或西班牙文。</span><span class="sxs-lookup"><span data-stu-id="74bf6-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="74bf6-111">如果您的組織是位於加拿大，您可以選擇 [英文] 和 [法文]。</span><span class="sxs-lookup"><span data-stu-id="74bf6-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="74bf6-112">如需支援的語言清單，請參閱[語音信箱問候語和來自商務用 Skype 的訊息的語言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="74bf6-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="74bf6-113">**變更個別使用者的語音信箱問候語和語音信箱訊息的語言。**</span><span class="sxs-lookup"><span data-stu-id="74bf6-113">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="74bf6-114">您可以變更使用者的首選 lanaguage，這會變更其語音信箱問候語和傳送至其 Outlook 信箱的語音信箱訊息的語言。</span><span class="sxs-lookup"><span data-stu-id="74bf6-114">You can change the preferred lanaguage for users, which will change the language of the their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="74bf6-115">如需指示，請參閱 [如何設定 Microsoft 365 或 Office 365 的語言和地區設定] （） https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region) 。</span><span class="sxs-lookup"><span data-stu-id="74bf6-115">For instruction please see [How to set language and region settings for Microsoft 365 or Office 365] (https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="74bf6-116">使用者可以透過在[Microsoft 商務用 Microsoft 365 中變更顯示語言和](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)時區中的指示，在登入後的設定中變更自己的問候語言</span><span class="sxs-lookup"><span data-stu-id="74bf6-116">Users can change their own greeting language through their settings after they sign in by following instructions found in [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="74bf6-117">**您想要錄製待發的語音信箱訊息嗎？**</span><span class="sxs-lookup"><span data-stu-id="74bf6-117">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="74bf6-118">請參閱[查看商務用 Skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="74bf6-118">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="74bf6-119">Microsoft 團隊-使用者可從 [[小組] 桌面用戶端設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)變更其語音信箱設定</span><span class="sxs-lookup"><span data-stu-id="74bf6-119">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="74bf6-120">**您想要變更語音信箱提示語言嗎？**</span><span class="sxs-lookup"><span data-stu-id="74bf6-120">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="74bf6-121">如果是商務用 Skype [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) ，請在 [**提示語言**] 下選擇新的語言。</span><span class="sxs-lookup"><span data-stu-id="74bf6-121">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="74bf6-122">Microsoft 團隊-使用者可以變更來自[小組桌面用戶端設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)的語音信箱問候語</span><span class="sxs-lookup"><span data-stu-id="74bf6-122">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="74bf6-123">變更組織中每個人的系統語言</span><span class="sxs-lookup"><span data-stu-id="74bf6-123">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="74bf6-124">使用您的[全域系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="74bf6-124">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="74bf6-125">在 Microsoft 365 系統管理中心，選擇 [**設定**  >  **設定**  >  **組織設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="74bf6-125">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![螢幕擷取畫面顯示選擇 [設定]，然後選擇 [組織設定檔]。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="74bf6-127">選擇 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="74bf6-127">Choose **Edit**.</span></span>
    
    ![顯示 [編輯] 選項的螢幕擷取畫面。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="74bf6-129">針對貴組織中的每個人，從 [**喜好語言**] 清單中選取一種語言。</span><span class="sxs-lookup"><span data-stu-id="74bf6-129">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="74bf6-130">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="74bf6-130">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="74bf6-131">系統管理員相關的文章</span><span class="sxs-lookup"><span data-stu-id="74bf6-131">Related articles for the admin</span></span>

- [<span data-ttu-id="74bf6-132">電話系統和通話方案</span><span class="sxs-lookup"><span data-stu-id="74bf6-132">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="74bf6-133">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="74bf6-133">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="74bf6-134">在商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Microsoft 365 或 Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="74bf6-134">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="74bf6-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="74bf6-135">Related topics</span></span>

- [<span data-ttu-id="74bf6-136">在 Microsoft 365 或 Office 365 for Business 中變更您的顯示語言和時區</span><span class="sxs-lookup"><span data-stu-id="74bf6-136">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="74bf6-137">[在 Office 2010 及更新版本中新增語言或設定語言喜好設定](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="74bf6-137">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="74bf6-138">啟用或變更鍵盤配置語言</span><span class="sxs-lookup"><span data-stu-id="74bf6-138">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 

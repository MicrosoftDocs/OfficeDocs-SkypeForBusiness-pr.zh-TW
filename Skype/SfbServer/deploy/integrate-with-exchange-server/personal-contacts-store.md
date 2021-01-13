---
title: 在 Lync 2010 用戶端電腦上設定個人連絡人存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要：設定舊版用戶端所使用的個人連絡人存放區。
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833933"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="400af-103">在 Lync 2010 用戶端電腦上設定個人連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="400af-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="400af-104">如果您要整合商務用 Skype Server 2015 和 Exchange Server 2016 或 Exchange Server 2013，則應該設定用戶端所使用的個人連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="400af-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="400af-105">尤其是，您應該將商務用 Skype 設定為使用 Exchange 做為個人連絡人存放區，並同時確定使用者無法覆寫該決策。</span><span class="sxs-lookup"><span data-stu-id="400af-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="400af-106">您可以在每一部用戶端電腦上建立及設定登錄值，以完成此動作。</span><span class="sxs-lookup"><span data-stu-id="400af-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="400af-107">下列程式只需要使用 Lync 2010 用戶端或更早版本的用戶端。</span><span class="sxs-lookup"><span data-stu-id="400af-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="400af-108">Lync 2013 用戶端和所有商務用 Skype 用戶端將無法選擇覆寫連絡人存放區設定。</span><span class="sxs-lookup"><span data-stu-id="400af-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="400af-109">若要在單一電腦上設定此值，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="400af-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="400af-110">在用戶端電腦上，按一下 [ **開始** ]，然後按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="400af-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="400af-111">在 [執行] 對話方塊中，輸入 regedit，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="400af-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="400af-112">在 [登錄編輯程式] 中，展開 [ **HKEY_LOCAL_MACHINE**]、[ **軟體**]、[ **原則**]、[ **Microsoft**]，然後展開 [ **Communicator**]。</span><span class="sxs-lookup"><span data-stu-id="400af-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="400af-113">以滑鼠右鍵按一下 [ **Communicator**]，指向 [ **新增**]，然後按一下 [ **DWORD (32-bit) 值**]。</span><span class="sxs-lookup"><span data-stu-id="400af-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="400af-114">建立新值後，輸入 PersonalContactStoreOverride，然後按 ENTER 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="400af-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="400af-115">確認 PersonalContactStoreOverride 的值設為0，然後關閉 [登錄編輯程式]。</span><span class="sxs-lookup"><span data-stu-id="400af-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="400af-116">如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="400af-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="400af-117">如需在 Windows 10 中執行此動作的詳細資訊，請參閱 [建立群組原則物件](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) 文章。</span><span class="sxs-lookup"><span data-stu-id="400af-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  

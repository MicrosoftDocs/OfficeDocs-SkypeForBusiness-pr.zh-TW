---
title: Microsoft Teams 中的共用頻道錯誤
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用修正共用頻道中的錯誤。
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024142"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Microsoft Teams 中的共用頻道錯誤

如果您的使用者在嘗試將組織外部的人員新增至共用頻道時看到錯誤訊息，請檢查本文中的設定。 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>由於系統管理原則，您無法將外部人員新增至頻道。 如需詳細資訊，請與您的系統管理員連絡。

Teams 會使用Microsoft 365 群組加入團隊成員資格。 您必須開啟Microsoft 365 群組來賓設定，組織外部的人員才能新增至共用頻道。 如果您的使用者看到此錯誤，請檢查組織外部人員的Microsoft 365 群組設定。

為組織外部人員設定Microsoft 365 群組設定
1. 在Microsoft 365 系統管理中心的左側流覽窗格中，展開 **[設定]**。
1. 按一下 **[組織設定]**。
1. 在清單中，按一下 **[Microsoft 365 群組]**。
1. 請確定已核取 [**讓群組擁有者將組織外部的人員新增為來賓Microsoft 365 群組**] 和 [**讓來賓群組成員存取群組內容**] 核取方塊。
1. 如果您做了變更，請按一下 [ **儲存變更]**。

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>由於系統管理原則，您無法將外部人員新增至頻道

Teams 頻道原則決定使用者可以如何與共享頻道互動。 如果使用者看到此錯誤訊息，請檢查該使用者的頻道原則。

設定邀請組織外部人員加入共用頻道的原則
1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 Teams > Teams 原則。
1. 選取指派給使用者的原則。
1. 確定已 **開啟** **[邀請外部使用者加入共用頻道**]。
1. 如果您做了變更，請選取 [ **套用]**。

如需 Teams 頻道原則的詳細資訊，請參閱 [管理 Microsoft Teams 中的頻道原則](teams-policies.md)。

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>您無法與此組織中的人員共用此頻道

如果您的使用者看到此錯誤，則 Azure Active Directory 跨租使用者存取設定會阻止使用者與其他組織中的人員共用頻道。 這可能是因為貴組織中的輸入設定或其他組織中的輸出設定。

檢查貴組織的輸入設定
1. 在 [Azure Active Directory 中](https://aad.portal.azure.com)，選取 **[外部身分識別**]，然後選取 [ **跨租使用者存取設定]**。
1. 選取您要檢查之組織的輸入存取連結。
1. 在 **[B2B 直接連線] 索** 引標籤上，選擇 [ **自訂設定]**。
1. 在 [ **外部使用者和群組** ] 索引標籤上，確定已選取 [ **允許存取** ] 和 [ **所有外部使用者和群組** ]，或者如果您已選擇 **[選取外部使用者和群組**]，請確定受邀的使用者是所選群組的成員。
1. 如果您做了變更，請選取 [ **儲存** ]，然後關閉 [ **輸入存取設定] 刀** 鋒。

如果使用者持續看到錯誤，請洽詢其共同作業的組織。 該組織的輸出設定可能會不允許與您的組織共用。 如需設定組織間共用頻道的相關資訊，請參閱 [在共用頻道中與外部參與者共同作業](/microsoft-365/solutions/collaborate-teams-direct-connect)。

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>找不到任何相符專案。 確定電子郵件地址正確無誤，或與您的系統管理員連絡

如果您的使用者看到此錯誤，則 Microsoft 365 無法在外部組織中找到指定的電子郵件地址。 您必須向外部組織確認位址。


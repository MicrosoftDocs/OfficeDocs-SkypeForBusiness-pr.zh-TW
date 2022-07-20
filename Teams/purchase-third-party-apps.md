---
title: 購買適用于 Teams 的協力廠商應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: 瞭解如何使用信用卡、轉帳卡或發票帳單，從 Teams 市集購買協力廠商應用程式。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880237"
---
# <a name="purchase-third-party-apps-for-teams"></a>購買適用于 Teams 的協力廠商應用程式

Teams 應用程式可免費安裝，部分應用程式可能需要購買服務訂閱才能體驗應用程式的完整功能和範圍。 這些服務訂閱稱為「軟體即服務 (SaaS) 優惠，可透過 [AppSource](https://appsource.microsoft.com/) 購買，現在可透過 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)購買。

Microsoft Teams 系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面可讓您檢視和管理貴組織的所有 Teams 應用程式。 例如，您可以查看應用程式的組織層級狀態和屬性、將新的自訂應用程式上傳到貴組織的應用程式存放區、在組織層級封鎖或允許應用程式，以及管理整個組織的應用程式設定。

您也可以在這裡為貴組織中的使用者購買協力廠商應用程式所提供的服務授權。 資料表中的 **[授權]** 欄會指出應用程式是否提供 SaaS 訂閱以供購買。

![[購買授權管理應用程式] 頁面的螢幕擷取畫面。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>在 Teams 系統管理中心購買應用程式

> [!IMPORTANT]
> 當您啟用應用程式購買時，它也會開啟應用程式內購買。 使用者可能會看到 App 內購買優惠，這些優惠是由其應用程式的 ISV 所控制。 如果您想要封鎖使用者購買應用程式，您必須封鎖該應用程式。 如需如何封鎖應用程式的詳細資訊，請參閱 [管理應用程式原則](app-policies.md) 或 [瞭解如何在組織層級封鎖應用程式](manage-apps.md#allow-and-block-apps)。

1. 在 Microsoft Teams 系統管理中心的左窗格中，移至 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。 您必須是全域系統管理員或 Teams 服務系統管理員才能存取頁面。

1. 依應用程式名稱搜尋您想要的應用程式。 若要識別擁有付費 SaaS 訂閱的應用程式，請查看 **[授權] 欄** 。 每個應用程式都有下列其中一個值：
    * **購買**：此應用程式提供 SaaS 訂閱，且可供購買。  
    * **已購買**：應用程式提供 SaaS 訂閱，而且您已購買該訂閱的授權。
    * **- -**：應用程式不提供 SaaS 訂閱。

1. 當您找到應用程式時，選取 **[購買** ] 以移至應用程式詳細資料頁面的 [ **方案與價格** ] 索引標籤。 檢閱應用程式 SaaS 優惠方案的方案和定價資訊。 如果您需要更多資訊，請選取 **[深入瞭解]** 以移至 [AppSource 上的應用程式](https://appsource.microsoft.com/)頁面。

   > [!NOTE]
   > 私人方案也可能會列在購買清單中，包括貴組織先前與 ISV 所洽詢的特殊定價。 這些方案會在計畫名稱底下顯示「 **私人計畫** 」標籤。

1. 若要訂閱應用程式，請選擇您想要的方案，然後選取 [ **購買]**。 結帳流程會直接在 Teams 系統管理中心開啟。

1. 選取您要購買的使用者授權數目。

1. 確認帳單帳戶和購買人位址正確無誤。 如果您還沒有帳戶，請選取 [ **新增]**。 如需帳單帳戶的詳細資訊，請 [參閱瞭解帳單帳戶](/microsoft-365/commerce/manage-billing-accounts)。

   > [!NOTE]
   > 只有全域管理員可以新增帳單帳戶。

1. 確認已選取正確的帳單設定檔。 如果您還沒有新帳戶，請選取 **[新增]**。 您可以選擇使用信用卡、轉帳卡或 [發票帳單付款](#invoice-billing)。 帳單設定檔也可讓您新增採購單編號，以便日後識別您的訂單。 如需帳單設定檔的詳細資訊，請 [參閱瞭解帳單設定檔](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。

1. 選 **取 [下單]**。

1. 選 **取 [設定]** 以在發行者的網站上啟用您的訂閱。 如果您未在購買後設定訂閱，您可以稍後選取 **[管理授權]**。

購買與 Teams 應用程式相關聯的 SaaS 優惠之後，您可以在應用程式詳細資料頁面的 [ **方案] 和 [定價** ] 索引標籤上檢視下列購買詳細資料。

* **授權啟用日期**：您的授權啟用日期。 如果您的帳戶尚未設定，它會顯示為 **訂閱擱置中啟用**。
* **授權**：您購買的授權數目。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Teams 系統管理中心應用程式詳細資料頁面上 [方案] 和 [定價] 索引標籤的螢幕擷取畫面。":::

若要檢視和管理您購買的授權，請選取 **[管理授權**] 以存取Microsoft 365 系統管理中心。

全域系統管理員可以新增更多授權、移除授權，以及取消由組織中任何人購買的訂閱。 Teams 服務系統管理員可以針對自己購買的專案執行相同的動作。 不過，如果 Teams 服務系統管理員也有計費系統管理員角色，他們可以管理組織中任何人所購買的專案。

> [!NOTE]
> 如果全域管理員想要管理另一個全球管理員購買的訂閱，他們必須位於相同的帳單帳戶中。 您可以在Microsoft 365 系統管理中心中選取應用程式，提供您所購買之訂閱的另一個全[局管理員](https://admin.microsoft.com)存取權。 從該處，移至檢 **視帳單設定檔**  >  **選取計費帳戶**  >  **指派角色**  >  **新增其他全域系統管理員**。

### <a name="invoice-billing"></a>發票帳單

* 帳單計費可做為某些交易的付款選項。
* 您第一次使用發票計費時需要信用檢閱，最多可能需要 24 到 48 小時來核准。 在信用查核完成之前，無法使用發票計費。 您可以使用信用卡下單，或稍後在信用查閱核准後再試一次。
* 發票帳單僅適用于全域系統管理員或同時具備 Teams 服務系統管理員和計費系統管理員許可權的系統管理員。
* 購買具有 30 天免費試用版的方案時，無法使用發票帳單。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>列出並銷售 Teams 應用程式的 SaaS 優惠

開發人員可以建立與其 Teams 應用程式相關聯的 SaaS 優惠。 這些優惠會透過 [合作夥伴中心](https://partner.microsoft.com) 發佈，並可讓組織透過 [AppSource](https://appsource.microsoft.com/) 和 Microsoft Teams 系統管理中心購買。

如需適用于協力廠商應用程式開發人員的詳細資訊，請參閱 [建立 SaaS 優惠](/azure/marketplace/partner-center-portal/create-new-saas-offer)。

## <a name="related-articles"></a>相關文章

* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [建立 SaaS 優惠](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 內建角色](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)

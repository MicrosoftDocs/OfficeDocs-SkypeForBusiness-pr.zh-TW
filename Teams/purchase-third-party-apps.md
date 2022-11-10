---
title: 購買協力廠商應用程式及管理訂閱
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, nsuter
search.appverid: MET150
f1keywords: ''
description: 瞭解如何在 Teams 市集中使用信用卡、轉帳卡或發票帳單購買付費應用程式授權。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 82364d5659009e067a6884551266c6fabf93dc04
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912422"
---
# <a name="purchase-third-party-teams-apps-and-manage-subscriptions"></a>購買協力廠商 Teams 應用程式及管理訂閱

某些 Teams 應用程式可能需要購買服務訂閱，才能體驗應用程式的完整功能和範圍。 這些服務訂閱稱為軟體即服務 (SaaS) 優惠。 授權可透過 [AppSource](https://appsource.microsoft.com/) 和 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)購買。

付費應用程式是使用與任何其他應用程式相同的控管控制來管理。 您可以從 Teams 系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面檢視和管理所有 Teams 應用程式。

在 [管理應用程式] 頁面上，您也可以為組織中的使用者購買協力廠商應用程式所提供的服務授權。 資料表中的 **[授權]** 欄會指出應用程式是否提供 SaaS 訂閱以供購買。 使用者可以使用信用卡、轉帳卡或發票帳單來購買應用程式。

:::image type="content" source="media/manage-apps-new-page.png" alt-text="顯示 Teams 系統管理中心 [管理應用程式] 頁面上 [購買授權] 選項的螢幕擷取畫面。" lightbox="media/manage-apps-new-page-large.png":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>在 Teams 系統管理中心購買應用程式

若要在 Teams 系統管理中心購買應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。 您必須為全域管理員或 Teams 服務系統管理員，才能存取頁面。

1. 依應用程式名稱搜尋您想要的應用程式。 若要檢查應用程式是否提供付費的 SaaS 訂閱，請參閱 **授權** 欄。 每個應用程式都有下列其中一個值：
    * **購買**：此應用程式提供 SaaS 訂閱且可供購買。
    * **已購買**：應用程式提供 SaaS 訂閱，您已經為購買了其權限。
    * **- -**：應用程式不提供 SaaS 訂閱。

1. 選 **取 [購買** ] 以移至應用程式詳細資料頁面的 [ **方案與價格** ] 索引標籤。 您可以檢閱系統管理中心中可用的方案和定價資訊。 您可以選取 **[深入瞭解** 連結] 以移至 [AppSource 上的應用程式](https://appsource.microsoft.com/)頁面。

1. 若要訂閱應用程式，請選擇您想要的方案，然後選取 **[購買]**。 結帳流程會直接在 Teams 系統管理中心開啟。

> [!NOTE]
> 私人方案也可能會列在購買清單中，包括貴組織可以個別與應用程式開發人員協商的特殊價格。 這類方案會在方案名稱底下顯示 **[私人計劃]** 標籤。

1. 選取您想要購買的使用者授權數目。

1. 驗證帳單帳戶和購買人位址正確無誤。 如果您還沒有帳戶，請選取 **[新增]**。 如需帳單帳戶的詳細資訊，請參閱[了解帳單帳戶](/microsoft-365/commerce/manage-billing-accounts)。 只有全域管理員可以新增帳單帳戶。

1. 驗證是否已選取正確的帳單設定檔。 如果您還沒有新帳戶，請選取 **[新增]**。 您可以使用信用卡、轉帳卡或 [發票帳單付款](#invoice-billing)。 帳單設定檔也可讓您新增採購單編號，以在稍後識別您的訂單。 如需帳單設定檔的詳細資訊，請參閱[了解帳單設定檔](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。

1. 選取 **[下單]**。

1. 選取 **[設定]** 以在應用程式開發人員網站上啟用您訂閱。 如果您未在購買後設定訂閱，您可以稍後選取 **[管理訂閱]**。

購買與 Teams 應用程式相關聯的 SaaS 優惠之後，您可以在應用程式詳細資料頁面的 [ **方案與訂閱** ] 索引標籤上檢視下列購買詳細資料。

* **授權啟用日期**：您的授權啟用之日期。
* **授權**：您購買的授權數目。

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Teams 系統管理中心應用程式詳細資料頁面上 [方案和價格] 索引標籤的螢幕擷取畫面。" lightbox="media/purchase-third-party-apps-details-page.png":::

選 **取 [管理訂閱]** 以檢視和管理您購買的授權。

全域系統管理員可以檢視組織中任何人購買的訂閱，但他們只能新增更多授權、移除授權，以及取消任何人在其帳單帳戶中購買的訂閱。 Teams 服務系統管理員可以針對自己進行的購買執行相同的動作。

> [!NOTE]
> 如果全域系統管理員想要管理另一個全域系統管理員購買的訂閱，他們必須位於相同的帳單帳戶中。 您可以在[ Microsoft 365 系統管理中心](https://admin.microsoft.com)中選取應用程式，提供您所購買之訂閱的另一個全域系統管理員存取權。 在系統管理中心，存取 **檢視帳單設定檔** >  **選取計費帳戶** > **指派角色**  >  **新增其他全域系統管理員**。

> [!IMPORTANT]
> 當您啟用應用程式購買時，它也會啟用應用程式內購買。 使用者可能會看到應用程式內購買優惠，這些優惠是由其應用程式的應用程式開發人員所控制。 若要阻止使用者購買應用程式，您必須封鎖該應用程式。

### <a name="invoice-billing"></a>發票結算

* 發票結算可做為某些交易的付款選項。
* 您第一次使用發票結算時需要信用檢閱，最多可能需要 24 到 48 小時來核准。 在信用查核完成之前，無法使用發票結算。 您可以使用信用卡下單，或稍後在信用檢閱核准後再試一次。
* 發票結算僅適用於全域系統管理員或同時具備 Teams 服務系統管理員和計費系統管理員權限的系統管理員。
* 購買具有 30 天免費試用版的方案時，無法使用發票結算。

## <a name="manage-subscriptions-in-teams-admin-center"></a>在 Teams 系統管理中心管理訂閱

在 Teams 系統管理中心，您可以管理您購買的應用程式訂閱和授權。 您可以檢視應用程式訂閱清單及其詳細資料，並執行下列動作：

* 變更計畫
* 購買或移除授權
* 更新付款條件
* 取消訂閱
* 檢視您的發票

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="應用程式訂閱詳細資料的螢幕擷取畫面。" lightbox="media/manage-existing-subscriptions-all.png":::

若要管理訂閱，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  [**管理應用程式**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 選取 [ **訂閱] 索引** 標籤以檢視您購買的訂閱。

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="[管理應用程式] 頁面中應用程式訂閱選項的螢幕擷取畫面。" lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> 在 Teams 系統管理中心，您可以管理您或其他屬於相同帳單帳戶的系統管理員所購買的應用程式訂閱。 若要檢視其他系統管理員為同一租使用者購買或使用不同計費帳戶購買的所有應用程式訂閱，請流覽[Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home#/homepage)。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>列出並銷售 Teams 應用程式的 SaaS 供應項目

開發人員可以建立與其 Teams 應用程式相關聯的 SaaS 供應項目。 這些供應項目會透過 [合作夥伴中心](https://partner.microsoft.com) 發佈，並可讓組織透過 [AppSource](https://appsource.microsoft.com/) 和 Microsoft Teams 系統管理中心購買。

如需適用於協力廠商應用程式開發人員的詳細資訊，請參閱 [建立 SaaS 供應項目](/azure/marketplace/partner-center-portal/create-new-saas-offer)。

## <a name="related-articles"></a>相關文章

* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [建立 SaaS 供應項目](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 內建角色](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)

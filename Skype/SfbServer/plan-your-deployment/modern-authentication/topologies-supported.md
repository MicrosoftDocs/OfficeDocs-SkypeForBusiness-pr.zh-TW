---
title: 新式驗證支援的商務用 Skype 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出商務用 Skype 中的新式驗證支援的線上和內部部署拓撲，以及適用于每個拓撲的安全性功能。
ms.openlocfilehash: 443980f6ecf2bdf170974bf0fdc0dd64f3657e67
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219693"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>新式驗證支援的商務用 Skype 拓撲

本文列出商務用 Skype 中的新式驗證支援的線上和內部部署拓撲，以及適用于每個拓撲的安全性功能。

## <a name="modern-authentication-in-skype-for-business"></a>商務用 Skype 中的新式驗證

商務用 Skype 可利用新式驗證的安全性優勢。 因為商務用 Skype 與 Exchange 緊密合作，所以商務用 Skype 用戶端使用者看到的登入行為也會受到 Exchange MA 狀態的影響。 如果您有商務用 Skype 拆分網域混合，也會套用這種功能。 這是許多不斷移動的元件，但這裡的目標是可輕鬆顯示支援拓撲的清單。

指定商務用 Skype、商務用 Skype online、Exchange Server 和 Exchange online 時，MA 支援哪些拓撲？

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>商務用 Skype 中支援的 MA 拓撲

有可能兩部伺服器應用程式，以及兩部 Microsoft 365 或 Office 365 的工作負載，與 MA 使用的商務用 Skype 拓撲有關。

- 商務用 Skype server （CU 5）內部部署

- 商務用 Skype online （SFBO）

- Exchange server 內部部署

- Exchange server online （EXO）

MA 的另一個重要部分是瞭解使用者的驗證（authN）和授權（授權）的發生位置。 這兩個選項如下：

- Microsoft Cloud 中的 Azure AD，線上

- Active Directory 同盟伺服器（ADFS）內部部署

因此，它看起來像這樣，在雲端中使用 EXO 和 SFBO，使用 Azure AD，Exchange Server （NM-EXCH-UM-2ND）和商務用 Skype Server （SFB）位於-部署。

![開啟 MA 時，所有應用程式（Exchange 和商務用 Skype）和工作負載（EXO 和 SFBO）的範例，以及可參與的授權伺服器（ADFS 和 evoSTS）。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

以下是支援的拓撲。 請記下圖形的關鍵字：

- 如果圖示變成灰色或灰色，則不會在案例中使用。

- EXO 為 Exchange Online。

- SFBO 是商務用 Skype Online。

- NM-EXCH-UM-2ND 是 Exchange 內部部署。

- SFB 是商務用 Skype 內部部署。

- 授權伺服器是以三角形表示，例如，Azure AD 是具有雲端的三角形。

- 箭號指用戶端嘗試到達指定的伺服器資源時將使用的授權伺服器。

首先，讓我們在僅限內部部署或僅限雲端的拓撲中，使用商務用 Skype 的功能。

> [!IMPORTANT]
> 您是否準備好在商務用 Skype Online 中設定新式驗證？ 啟用此功能的步驟會在[這裡](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)靠右。

|拓撲名稱  <br/> |範例  <br/> |描述  <br/> |支援  <br/> |
|:-----|:-----|:-----|:-----|
|僅限雲端  <br/> |![僅限具有 MA 拓撲的支援 SFB （僅限雲端）。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)使用者駐留/信箱位於：線上  <br/> |MA 同時適用于 EXO 和 SFBO。  <br/> 因此，授權伺服器是 Azure AD。  <br/> |多重要素驗證（MFA）、用戶端憑證型驗證（CBA）、條件式存取（CA）/Mobile 應用程式管理（MAM）搭配 Intune。 \*  <br/> |
|僅限部署  <br/> |![僅限內部部署的 MA 拓撲支援的 SFB。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)位於下列位置的使用者駐留/信箱：內部部署  <br/> |MA 已開啟，供 SFB 內部部署。  <br/> 因此，授權伺服器為 ADFS。  <br/> 如需設定詳細資料，請參閱[本文。](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA （僅限 Windows 桌面-不支援行動用戶端）。 無 Exchange 整合功能。  <br/><p> **我們不建議採用這種方法。請參閱下列內容：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> 建議您在不同的商務用 Skype 和 Exchange （及其線上對應）中，避免出現提示數目的 MA 狀態。

混合式拓撲包含 SFB 分割網域混合式的組合。 這些是目前支援的混合拓撲：

|拓撲名稱  <br/> |範例  <br/> |描述  <br/> |支援  <br/> |
|:-----|:-----|:-----|:-----|
|混合1  <br/> |![支援的 SFB，含 MA 拓撲，混合式1（EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 使用者駐留/信箱位於： EXO 和 SFB  <br/> |SFB 未啟用 MA;此拓撲中未提供 SFB MA 功能。  <br/> |SFB 沒有 MA 功能。  <br/> |
|混合2  <br/> |![支援的 MA 與 S4B 混合拓撲2、SFBO，以及使用 NM-EXCH-UM-2ND on 部署的 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 使用者駐留/信箱位於： NM-EXCH-UM-2ND 和 SFBO  <br/> |僅適用于 SFBO 的 MA 為開啟。 授權伺服器是指位於 SFBO 的使用者的 Azure AD，但適用于 NM-EXCH-UM-2ND 內部部署的 AD。  <br/> |MFA，CBA，CA/MAM 搭配 Intune。\*  <br/> |
|混合3  <br/> |![支援的 MA 與 SFB，EXO 搭配 MA 開啟，加上 NM-EXCH-UM-2ND 和 SFB 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 使用者駐留/信箱位於： EXO + SFB，或 NM-EXCH-UM-2ND + SFB  <br/> |此拓撲中無可用的 SFB MA 功能  <br/> |SFB 沒有 MA 功能。  <br/> |
|混合4  <br/> |![支援的 MA 與 SFB、SFBO 和 MA 開啟，加上 NM-EXCH-UM-2ND 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 使用者駐留/信箱位於： NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB  <br/> |MA 已開啟為 SFBO，因此授權伺服器是指位於 SFBO 之使用者的 Azure AD。 部署中的使用者在 SFB 和 EXO 使用 AD。  <br/> |僅限使用 Intune for online 使用者的 MFA、CBA、CA/MAM。\*  <br/> |
|混合5  <br/> |![SFB 中支援的 MA、EXO 搭配 MA，以及 SFBO 搭配 MA，以及 NM-EXCH-UM-2ND 及 SFB 內部部署。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB  <br/> |MA 在 EXO 和 SFBO 中皆開啟，因此授權伺服器是位於 SFBO 中使用者的 Azure AD;部署中的使用者在 NM-EXCH-UM-2ND 和 SFB 使用 AD。  <br/> |僅限使用 Intune for online 使用者的 MFA、CBA、CA/MAM。\*  <br/> |
|混合6  <br/> |![在混合式6拓撲中，新式驗證是在所有的四個 possibile 位置上，而是現代驗證時則是理想的 situtation。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB  <br/> |MA 是在所有位置，因此授權伺服器是針對所有使用者的 Azure AD。 （線上和內部部署）  <br/>  如需 [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) 部署步驟，請參閱。 <br/> |所有使用者的 MFA、CBA 及 CA/MAM （透過 Intune）。  <br/> |

\*-MFA 包括 Windows Desktop、MAC、iOS、Android 裝置和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 裝置;具有 Intune 的 CA/MAM 包含 Android 和 iOS 裝置。

> [!IMPORTANT]
> 請務必注意，在某些情況下，使用者可能會看到**多個提示**，特別是，所有混合式拓撲的伺服器資源都不會有相同的 MA 狀態的情況。

> [!IMPORTANT]
> 另外請注意，在某些情況下（混合式1、3和5），必須針對 Windows 桌面用戶端適當設定[AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼。



---
title: 與 Exchange 和 SharePoint 的整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 摘要：瞭解商務用 Skype Server 2015 與 Exchange 和 SharePoint 整合的相關資訊。
ms.openlocfilehash: 9d5f665d5bffede2de10c77735ea76fe55337af8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799803"
---
# <a name="integration-with-exchange-and-sharepoint"></a>與 Exchange 和 SharePoint 的整合

**摘要：** 瞭解商務用 Skype Server 2015 與 Exchange 和 SharePoint 整合的相關資訊。

您可以設定商務用 Skype Server 2015 部署，以與 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server （內部部署和線上）整合。 除非另外指定，否則所有用戶端都支援下表所列的功能。 如需有關用戶端支援的詳細資訊，請參閱商務用 skype 與商務用 skype Online 用戶端的[桌面用戶端功能比較](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)（商務用[Skype online 的客戶](https://go.microsoft.com/fwlink/p/?LinkId=281902)端比較表）。

## <a name="integration-with-exchange-server"></a>與 Exchange Server 整合

下清單格列出整合至 Microsoft Exchange Server 時，混合式部署中支援的功能。

 **內部部署與 Exchange 內部部署中的商務用 Skype 伺服器**


|**功能**|**筆記**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱[IM 和目前狀態](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|透過 Outlook 排程及加入線上會議  <br/> |如需詳細資訊，請參閱將[商務用 Skype Server 2015 與 Exchange Server 整合](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Outlook Web App 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱[在商務用 Skype Server 2015 中設定混合式環境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|透過 Outlook Web App 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端中加入線上會議  <br/> |如需詳細資訊，請參閱[部署行動性](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)。  <br/> |
|根據 Outlook 行事曆空閒/忙碌資訊發佈狀態  <br/> ||
|連絡人清單（透過整合連絡人存放區）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> Lync 2013 或商務用 Skype 桌面用戶端是必要的。  <br/>  如需詳細資訊，請參閱[設定商務用 Skype Server 2015 以使用整合連絡人存放區](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|在 Lync 2013 用戶端、商務用 Skype 用戶端和 Lync Web App 中的高解析度連絡人相片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 如需詳細資訊，請參閱[在商務用 Skype Server 2015 中設定高解析度相片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 針對 MAC 版商務用 Skype 應用程式和行動裝置上的相片，必須按照在[商務用 Skype server 和 Exchange server 中設定合作夥伴應用程式](../deploy/integrate-with-exchange-server/configure-partner-applications.md)中的說明，設定商務用 skype server 2015 與 exchange server 之間的整合。 <br/> |
|會議委派  <br/> |只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。 如需詳細資訊，請參閱[商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|在 Exchange 中封存內容（IM 與會議）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 如需詳細資訊，請參閱[存檔的部署檢查清單](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜尋封存的內容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|語音信箱  <br/> |如需詳細資訊，請參閱[部署內部部署 EXCHANGE UM，以提供 Lync Server 2013 語音信箱](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。  <br/> |

 **內部部署與 Exchange Online 上的商務用 Skype 伺服器**


|**功能**|**筆記**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱[設定內部部署商務用 Skype Server 2015 與 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|透過 Outlook 排程及加入線上會議  <br/> ||
|Outlook Web App 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱[設定內部部署商務用 Skype Server 2015 與 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|從 Outlook Web App 排程及加入線上會議  <br/> |如需詳細資訊，請參閱[設定內部部署商務用 Skype Server 2015 與 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端中加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊發佈狀態  <br/> ||
|連絡人清單（透過 [整合連絡人存放區]）。  <br/> |僅限 Lync Server 2013。 Lync 2013 或商務用 Skype 桌面用戶端是必要的。  <br/> 如需詳細資訊，請參閱[設定商務用 Skype Server 2015 以使用整合連絡人存放區](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|在 Lync 2013 用戶端、商務用 Skype 用戶端和 Lync Web App 中的高解析度連絡人相片。  <br/> |如需詳細資訊，請參閱[在商務用 Skype Server 2015 中設定高解析度相片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 針對 MAC 版商務用 Skype 應用程式和行動裝置上的相片，您必須按照設定[內部部署商務用 Skype server 和 Outlook Web app 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md)中的說明，將商務用 skype server 2015 與 Exchange server 之間的整合設定完成。 <br/> |
|會議委派  <br/> |只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。 如需詳細資訊，請參閱[商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|未接的交談記錄和通話記錄會寫入使用者的 Exchange 信箱  <br/> ||
|在 Exchange 中封存內容（IM 與會議）  <br/> |如需詳細資訊，請參閱[存檔的部署檢查清單](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜尋封存的內容  <br/> |如需詳細資訊，請參閱[設定 SharePoint EDiscovery 中心的 Exchange](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|語音信箱  <br/> |如需詳細資訊，請參閱為[Lync Server 2013 使用者提供託管 EXCHANGE UM 的語音信箱](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)。  <br/> |

 **商務用 Skype Online 與 Exchange 內部部署**


|**功能**|**筆記**|
|:-----|:-----|
|在 Outlook 中的目前狀態  <br/> ||
|透過 Outlook 電子郵件的 IM、PSTN 通話、Skype 通話或視頻通話來回應  <br/> ||
|透過 Outlook 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端中加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊發佈狀態  <br/> ||
|未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|在 Lync 2013 或商務用 Skype 用戶端中的高解析度連絡人相片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 當使用者駐留在商務用 Skype Online 上時，Lync Web App 不支援此功能。  <br/> |
|會議委派  <br/> |只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。 如需詳細資訊，請參閱[商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|未接的交談記錄和通話記錄會寫入使用者的 Exchange 信箱  <br/> ||
|伺服器端交談歷程記錄  <br/> ||

 **商務用 Skype Online 和 Exchange Online**


|**功能**|**筆記**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> ||
|透過 Outlook 排程及加入線上會議  <br/> ||
|Outlook Web App 中的 IM/目前狀態  <br/> ||
|從 Outlook Web App 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端中加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊發佈狀態  <br/> ||
|未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|連絡人清單（透過整合連絡人存放區）  <br/> |需要 Lync Server 2013 或商務用 Skype 用戶端  <br/> |
|Lync 2013、商務用 Skype 用戶端和 Lync Web App 的高解析度連絡人相片  <br/> ||
|會議委派  <br/> |只有當兩個使用者都在同一個目錄林中進行線上，或者兩者都在內部部署時，才受支援。 如需詳細資訊，請參閱[商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|在 Exchange 中封存內容（IM 與會議）  <br/> ||
|搜尋封存的內容  <br/> ||
|語音信箱  <br/> ||

## <a name="integration-with-sharepoint"></a>與 SharePoint 整合

下表列出與 SharePoint 整合時，混合式部署中支援的功能。

||**SharePoint 內部部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**商務用 Skype Server 2015 內部部署** <br/> | 技能搜尋 <br/>  SharePoint 中的目前狀態 <br/> | SharePoint 中的目前狀態 <br/> |
|**商務用 Skype Online** <br/> | SharePoint 中的目前狀態 <br/> | SharePoint 中的目前狀態 <br/> |



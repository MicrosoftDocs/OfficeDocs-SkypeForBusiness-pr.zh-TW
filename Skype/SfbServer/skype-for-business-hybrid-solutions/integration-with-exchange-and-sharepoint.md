---
title: 與 Exchange 和 SharePoint 的整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：瞭解商務用 Skype Server 2015 與 Exchange 和 SharePoint 的整合。
ms.openlocfilehash: 01ebbdd94098fa9f7785f41fedbcbdfe7589f03e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092831"
---
# <a name="integration-with-exchange-and-sharepoint"></a>與 Exchange 和 SharePoint 的整合

**摘要：** 深入瞭解商務用 Skype Server 2015 與 Exchange 及 SharePoint 的整合。

您可以針對內部部署和線上，設定商務用 Skype Server 2015 部署，以與 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server 整合。 除非另有指定，否則下表中所列的功能會支援所有用戶端。 如需用戶端支援的詳細資訊，請參閱適用于商務用 skype [online 之用戶端](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)的商務用 Skype 和商務用 skype online 用戶端比較表的[桌面用戶端功能比較](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)。

## <a name="integration-with-exchange-server"></a>與 Exchange Server 整合

下表列出與 Microsoft Exchange Server 整合時，混合式部署支援的功能。

 **內部部署上的商務用 Skype 伺服器和 Exchange 內部部署**


|**功能**|**附註**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱 [IM 和目前狀態](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|透過 Outlook 排程及加入線上會議  <br/> |如需詳細資訊，請參閱將 [商務用 Skype Server 2015 與 Exchange Server 整合](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Outlook Web App 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中設定混合式環境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|透過 Outlook Web App 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端加入線上會議  <br/> |如需詳細資訊，請參閱 [部署行動性](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)。  <br/> |
|根據 Outlook 行事曆空閒/忙碌資訊的發行狀態  <br/> ||
|透過整合連絡人存放區 (的連絡人清單)   <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 需要 Lync 2013 或商務用 Skype 桌面用戶端。  <br/>  如需詳細資訊，請參閱 [設定商務用 Skype Server 2015 以使用整合連絡人存放區](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 用戶端、商務用 Skype 用戶端和 Lync Web App 的高解析度連絡人相片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中設定高解析度相片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 針對適用于 MAC 和行動裝置之商務用 Skype 應用程式的相片，商務用 skype server [與 Exchange server 中的「設定夥伴應用程式](../deploy/integrate-with-exchange-server/configure-partner-applications.md)」所述，必須設定商務用 skype server 2015 和 exchange server 之間的整合。 <br/> |
|會議委派  <br/> |只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。 如需詳細資訊，請參閱 [商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|在 Exchange 中封存內容 (IM 和會議)   <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 如需詳細資訊，請參閱封存 [的部署檢查清單](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|搜尋封存的內容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|語音信箱  <br/> |如需詳細資訊，請參閱 [部署 On-Premises EXCHANGE UM 以提供 Lync Server 2013 語音信箱](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **商務用 Skype Server 內部部署和 Exchange Online**


|**功能**|**附註**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱 [設定內部部署商務用 Skype Server 2015 和 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|透過 Outlook 排程及加入線上會議  <br/> ||
|Outlook Web App 中的 IM/目前狀態  <br/> |如需詳細資訊，請參閱 [設定內部部署商務用 Skype Server 2015 和 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|從 Outlook Web App 排程及加入線上會議  <br/> |如需詳細資訊，請參閱 [設定內部部署商務用 Skype Server 2015 和 Outlook Web App 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊的發行狀態  <br/> ||
|透過整合連絡人存放區)  (的連絡人清單。  <br/> |僅限 Lync Server 2013。 需要 Lync 2013 或商務用 Skype 桌面用戶端。  <br/> 如需詳細資訊，請參閱 [設定商務用 Skype Server 2015 以使用整合連絡人存放區](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 用戶端、商務用 Skype 用戶端和 Lync Web App 的高解析度連絡人相片。  <br/> |如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中設定高解析度相片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 針對適用于 MAC 和行動裝置之商務用 Skype 應用程式的相片，商務用 skype server 2015 和 Exchange Server 之間的整合，必須依照設定 [內部部署商務用 Skype server 與 Outlook Web app 之間的整合](../deploy/integrate-with-exchange-server/outlook-web-app.md)所述進行設定。 <br/> |
|會議委派  <br/> |只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。 如需詳細資訊，請參閱 [商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|錯過的交談記錄及通話記錄會寫入使用者的 Exchange 信箱  <br/> ||
|在 Exchange 中封存內容 (IM 和會議)   <br/> |如需詳細資訊，請參閱封存 [的部署檢查清單](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|搜尋封存的內容  <br/> |如需詳細資訊，請參閱 [Configure Exchange for SharePoint EDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|語音信箱  <br/> |如需詳細資訊，請參閱 [在主控 EXCHANGE UM 上提供 Lync Server 2013 使用者語音信箱](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)。  <br/> |

 **商務用 Skype Online 和 Exchange 內部部署**


|**功能**|**附註**|
|:-----|:-----|
|Outlook 中的目前狀態  <br/> ||
|透過 IM、PSTN 通話、Skype 通話或來自 Outlook 電子郵件的視頻呼叫進行回應  <br/> ||
|透過 Outlook 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊的發行狀態  <br/> ||
|錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|Lync 2013 或商務用 Skype 用戶端的高解析度連絡人相片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 當使用者位於商務用 Skype Online 時，Lync Web App 不支援此功能。  <br/> |
|會議委派  <br/> |只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。 如需詳細資訊，請參閱 [商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|錯過的交談記錄及通話記錄會寫入使用者的 Exchange 信箱  <br/> ||
|伺服器端交談記錄  <br/> ||

 **商務用 Skype Online 和 Exchange Online**


|**功能**|**附註**|
|:-----|:-----|
|Outlook 中的 IM/目前狀態  <br/> ||
|透過 Outlook 排程及加入線上會議  <br/> ||
|Outlook Web App 中的 IM/目前狀態  <br/> ||
|從 Outlook Web App 排程及加入線上會議  <br/> ||
|行動用戶端中的 IM/目前狀態  <br/> ||
|在行動用戶端加入線上會議  <br/> ||
|根據 Outlook 行事曆空閒/忙碌資訊的發行狀態  <br/> ||
|錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱  <br/> ||
|透過整合連絡人存放區 (的連絡人清單)   <br/> |需要 Lync Server 2013 或商務用 Skype 用戶端  <br/> |
|Lync 2013、商務用 Skype 用戶端和 Lync Web App 的高解析度連絡人相片  <br/> ||
|會議委派  <br/> |只有在兩位使用者都位於相同樹系中的線上，或兩者都位於內部部署時，才受支援。 如需詳細資訊，請參閱 [商務用 Skype 混合式解決方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|在 Exchange 中封存內容 (IM 和會議)   <br/> ||
|搜尋封存的內容  <br/> ||
|語音信箱  <br/> ||

## <a name="integration-with-sharepoint"></a>與 SharePoint 整合

下表列出混合式部署中支援的功能（與 SharePoint 整合時）。

||**SharePoint 內部部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**商務用 Skype Server 2015 內部部署** <br/> | 技能搜尋 <br/>  目前狀態 SharePoint <br/> | 目前狀態 SharePoint <br/> |
|**商務用 Skype Online** <br/> | 目前狀態 SharePoint <br/> | 目前狀態 SharePoint <br/> |
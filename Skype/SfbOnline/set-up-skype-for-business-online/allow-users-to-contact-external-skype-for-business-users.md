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
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>允許使用者連絡外部商務用 Skype 使用者
  
在下列情況下，請使用本文中的步驟：
  
- 您的企業中有不同網域的使用者。 例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。

- 您希望貴組織中的人員可以使用商務用 Skype 與組織外部的特定企業中的人員聯繫。

- 您希望世界各地的其他人都能使用商務用 Skype，透過您的電子郵件地址找出並與您聯繫。 如果您與他們使用預設的商務用 Skype 設定，這將會自動運作。 如果不是，則必須確認他們的設定不會封鎖您的網域。

## <a name="enable-business-to-business-communications-for-your-users"></a>為使用者啟用企業對企業通訊

<a name="bk_preview"> </a>

您必須在兩家組織的 Microsoft 365 或 Office 365 中擁有系統 [管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ，才能進行這項通訊。

![](../images/teams-logo-30x30.png)**使用 [團隊管理中心**] 顯示 Microsoft 小組標誌的圖示
  
1. 使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登入。

2. 在系統管理中心中，移至 [系統**管理中心**]  >  **小組**。

    ![選擇 [團隊管理員]。](../images/MS-Teams-Admin.png)
  
3. 在 [**小組中心**] 中，選擇 [ **Skype** > **傳統版入口網站**] 
  ![ 選擇 [SfB 舊版入口網站]。](../images/SFBlegacy-size65.png)

4. 在 [商務用 Skype 系統管理中心]****，選擇 [組織]****  >  [外部通訊]****。
5. 若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]****。

    或者，如果您想要與世界各地擁有開啟商務用 Skype 原則的其他人通訊，請選擇 [ **除了封鎖的網域以外**]。 這是預設設定。

6. 在 [ **封鎖或允許的網域**] 下，選擇 **+** 並新增您要允許的功能變數名稱。

7. 確定其他組織中的系統管理員在 **商務用 Skype 系統管理中心**執行這些相同的步驟。 例如，在他們的 [ **允許的網域** ] 清單中，他們的管理員必須為您的企業輸入網域。

8. 如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。

    如果您的組織使用不同的防火牆解決方案來限制您網路上的電腦連線至網際網路，請確定您的用戶端電腦能夠存取下列 [Office 365 url 和 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。 這可能需要在防火牆或 proxy 基礎結構設定： ** \* . api.skype.com**、 \* **users.storage.live.com**和**graph.skype.com**中，將 fqdn 新增到輸出允許清單中。 如需如何在防火牆中開啟這些埠的相關指示，請參閱它隨附的檔。

    如需開啟所有埠的清單，請參閱 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。

9. 請確定組織中的系統管理員也已遵循這些步驟。

10. 請**等候長達24小時進行測試**。 當您變更 [外部通訊] 設定時，最多可能需要24小時的時間，才能在所有資料中心上填入這些變更。

![Skype ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 您可以讓使用者在使用 Skype 的所有人（免費消費者 app）中搜尋和傳送即時消息！ 若要深入瞭解，請參閱 [讓商務用 Skype 使用者新增 skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>測試和疑難排解

<a name="bk_preview"> </a>

 **當您設定企業對企業通訊時，最常遇到的問題就是將其 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) 直接取得正確。**
  
若要測試您的設定，您需要不在公司防火牆後的商務用 Skype 的連絡人。
  
1. 在您變更 [外部通訊] 設定之後，請 **等候長達24小時以進行測試**。

2. 在商務用 Skype 中，在商務用 Skype 中搜尋您的連絡人，然後傳送要求到聊天。

    如果您收到因公司原則無法傳送的訊息，您必須仔細檢查您的 [Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。

3. 要求您的商務用 Skype 連絡人向您傳送聊天的要求。 如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。

4. 測試問題是否為您防火牆的另一種方法，就是移至不在防火牆背後的 wifi 位置（例如咖啡廳）。 使用商務用 Skype 將要求傳送給您的連絡人以進行交談。 如果郵件在其中，但不在您的工作中，您知道問題是您的防火牆。

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>如何在與其他公司連線時找到其他人並找到其他人

<a name="bk_preview"> </a>

在您啟用與其他商務用 Skype 使用者的外部通訊之後，您的使用者就可以搜尋其登入名稱，找到聯盟的商務用 Skype 使用者。 Rob@contoso.com 就是一個範例。 接著他們將需要將人員新增至他們的連絡人清單。
  
![若要尋找同盟企業中的使用者，您必須搜尋其電子郵件地址 (通常也是他們的登入名稱) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>設定與同盟企業通訊的秘訣

<a name="bk_preview"> </a>

- 若要在商務用 Skype 2015 與商務用 Skype Online 之間設定同盟，請參閱這篇文章： [使用商務用 Skype Online 設定同盟](https://technet.microsoft.com/library/jj205126.aspx)。

- 若要在 Lync 與商務用 Skype Online 之間設定同盟，請參閱這篇文章：為 [Lync Online 客戶設定同盟支援](https://technet.microsoft.com/library/hh202193.aspx)。

- 當 Microsoft 365 或 Office 365 中的兩個商務用 Skype 使用者彼此通訊于不同的網域時，他們只能使用商務用 Skype 功能 (例如，在兩個組織中開啟的影片交談或桌面共用) 。

- 如果貴組織中的商務用 Skype 使用者已加入 In-Place 或訴訟封存，該使用者與其他商務用 Skype 或 Skype 使用者之間的任何 IM 交談，都會儲存在其信箱中的 **可復原專案** 中。 這些交談不會儲存在其信箱中的 [ **交談記錄** ] 資料夾中。

## <a name="turn-off-external-communication-for-specific-individuals"></a>關閉特定人員的外部通訊

<a name="bk_preview"> </a>

在您為整個企業啟用外部溝通之後，您就可以針對特定的人員關閉該功能。
  
1. 使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登入。

2. 在系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。

3. 在使用者清單中，選擇使用者，然後在 [ **其他設定**] 底下，按一下 [ **編輯商務用 Skype 屬性**]。

    ![選擇商務用 Skype](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 在 **商務用 Skype 系統管理中心**中，選擇 [ **外部通訊**]。

    在 [ **選項** ] 頁面上，將會選取所有選項。 清除您想要停用的通訊。 下列影像顯示 Jakob 將能夠與其他信任的公司中的人員通訊，但無法與其他 Skype 使用者通訊。

    ![選擇外部連絡人](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 選擇 [ **儲存**]。

> [!NOTE]
> 您可能需要等候長達24小時，變更才會生效。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相關主題

<a name="bk_preview"> </a>

[設定商務用 Skype Online](set-up-skype-for-business-online.md)
  
[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)
  
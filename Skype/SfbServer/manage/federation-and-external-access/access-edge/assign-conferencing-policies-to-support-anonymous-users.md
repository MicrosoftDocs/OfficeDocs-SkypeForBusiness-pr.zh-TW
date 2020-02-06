---
title: 指派會議原則以支援匿名使用者
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以將會議原則設定為支援匿名使用者，並將該會議原則套用到特定使用者，以控制誰能邀請匿名使用者。
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818414"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>指派會議原則以支援商務用 Skype Server 中的匿名使用者 


根據預設，所有使用者都會被禁止邀請匿名使用者參與會議。 您可以將會議原則設定為支援匿名使用者，並將該會議原則套用到特定使用者，以控制誰能邀請匿名使用者。 如需有關如何設定會議原則以支援匿名使用者的詳細資料，請參閱[在商務用 Skype server 中建立會議原則](../../conferencing/create-policies.md)以及[管理聯盟及外部存取權至商務用 skype 伺服器](../managing-federation-and-external-access.md)。

使用本節中的程式，將您已建立的會議原則套用至一或多個使用者或使用者群組。

> [!NOTE]  
> 除了設定及套用原則以讓使用者邀請匿名使用者，您也必須為貴組織啟用匿名使用者支援。 如需詳細資訊，請參閱[在商務用 Skype Server 中設定控制公用使用者存取權的原則](../external-access-policies/configure-policies-to-control-public-user-access.md)。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>設定匿名參與會議的使用者原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**會議**]，然後執行下列其中一項操作：
    
    1.  若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在 [Name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，允許與匿名使用者進行通訊的使用者原則**EnableAnonymous** ）。
    
    2.  若要設定現有的使用者原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

4.  在 [**會議原則**] 對話方塊中，選取 [**允許參與者邀請匿名使用者**] 核取方塊。

5.  按一下 [認可]****。

6.  在左側導覽列中，按一下 [**使用者**]，搜尋您要設定的使用者帳戶。

7.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

8.  在 [**會議原則**] 下的 [**編輯商務用 Skype Server 使用者**] 中，選取您想要套用至此使用者的 [匿名使用者存取設定] 使用者原則。  

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定，且由伺服器自動套用。


若要讓使用者邀請匿名使用者加入會議，您也必須在組織中啟用匿名使用者支援。 如需詳細資訊，請參閱[在商務用 Skype Server 中設定控制公用使用者存取權的原則](../external-access-policies/configure-policies-to-control-public-user-access.md)。


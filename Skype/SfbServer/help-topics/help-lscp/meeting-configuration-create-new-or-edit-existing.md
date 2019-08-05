---
title: '[會議設定] 建立新的或 [編輯現有]'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: '[會議設定] 設定會為使用者排程的會議定義使用者的加入體驗。 這些設定僅適用于排程的會議。 它們不適用於在用戶端中按一下 [立即開會] 選項所建立的即席會議。'
ms.openlocfilehash: baf8912e90d68dc175e6cd278cc7a13eff82ae33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192482"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>會議組態：建立新的或編輯現有組態

會議組態設定會定義由使用者安排之會議的使用者加入體驗。這些設定只適用於事先安排的會議，不適用於透過按一下用戶端中的 [立即開會]**** 選項所建立的臨時會議。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **範圍**識別您要建立或修改的會議設定範圍: [全域]、[網站] 或 [文件庫]。

- **名稱**會議配置預設會命名, 且無法變更名稱。

- **PSTN 呼叫者略過大廳**選取此核取方塊, 以自動准許使用公用交換電話網絡 (PSTN) 電話線路撥入會議的使用者。 清除此核取方塊可將 PSTN 呼叫者路由到會議廳, 直到會議簡報者准許他們存取會議為止。

- **指定為簡報者**選取使用者類別 (除了會議召集人), 在加入會議時, 系統會自動將其指定為簡報者。 無論這項設定為何, 在排程會議時, 簡報者都可以明確指定為簡報者, 或者可以在會議期間明確地將其升級為簡報者。 選項包括:

  - **None**如果召集人以外的任何人都不會自動指定為簡報者, 請選取此選項。

  - **公司**選取這個選項, 即可自動將組織的成員指定為簡報者。

  - **所有人**選取此選項可自動將任何人指定為簡報者。

- **預設為指派的會議類型**此設定會控制 Outlook 會議增益集是否總是使用召集人指派的會議來排程會議, 這表示排程的會議永遠具有相同的聯接 URL 和音訊資訊。 選取此核取方塊可讓排程的會議永遠使用相同的聯接 URL。 清除此核取方塊, 以針對每個會議使用不同的加入 URL。

- **預設會承認匿名使用者**如果是匿名 (也就是未獲驗證), 允許使用者預設出席會議, 請選取此核取方塊。 如果預設不允許匿名使用者出席會議, 請清除此核取方塊。

- **標誌 URL**輸入包含要用於自訂會議邀請之圖像的 URL。

- 說明**URL**輸入網站的 URL, 使用者可以在此取得加入會議的協助。

- **法律文字 URL**輸入含有該會議之法律資訊和免責聲明的網站 URL。

- **自訂頁尾文字**輸入要在自訂會議邀請上使用的文字。

如需使用會議設定的詳細資訊，請參閱作業文件中的〈[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)〉如需設定大型會議之會議設定的詳細資訊，請參閱規劃文件中的〈[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)〉。



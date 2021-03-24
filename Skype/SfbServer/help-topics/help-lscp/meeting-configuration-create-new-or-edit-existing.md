---
title: 會議設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 會議設定設定會為使用者排程的會議定義使用者加入體驗。 這些設定只適用于排程的會議。 在用戶端中按一下 [立即開會] 選項，不會套用至所建立的特定會議。
ms.openlocfilehash: 21cc12cd025edfc573e1e2f21ed08181f1a0c926
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099669"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>會議組態：建立新的或編輯現有組態

會議設定設定會為使用者排程的會議定義使用者加入體驗。 這些設定只適用于排程的會議。 在用戶端中按一下 [ **立即開會** ] 選項，不會套用至所建立的特定會議。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **範圍** 識別您要建立或修改之會議設定的範圍：全域、網站或集區。

- **名稱** 會議設定預設會以名稱命名，無法變更其名稱。

- **PSTN 呼叫者略過大廳** 選取此核取方塊，可自動承認透過公用交換電話網路 (PSTN) 電話線的方式撥打參加會議的使用者。 清除此核取方塊可將 PSTN 來電者路由傳送到會議廳，直到會議簡報者授與會議的訪問權為止。

- **指定為簡報者** 在會議召集人) 之外，選取使用者 (的類別，以在加入會議時自動將其指定為簡報者。 無論此設定為何，當會議排程時，簡報者都可以明確指定為簡報者，也可以在會議期間明確地將其提升為簡報者。 選項包括：

  - **無** 如果不是召集人的任何人自動指定為簡報者，請選取此選項。

  - **公司** 選取此選項可自動將組織的成員指定為簡報者。

  - **所有人** 選取此選項可自動將任何人指定為簡報者。

- **依預設指派會議類型** 此設定會控制 Outlook 會議 Addin 是否一定要使用召集人指派的會議來排程會議，也就是說，已排程的會議一定會有相同的加入 URL 和音訊資訊。 選取此核取方塊可讓已排程的會議永遠使用相同的 join URL。 清除此核取方塊可對每個會議使用不同的 join URL。

- **預設會承認匿名使用者** 如果匿名 (（也就是未驗證的) 使用者預設會獲准參加會議），請選取此核取方塊。 如果預設不允許匿名使用者參加會議，請清除此核取方塊。

- **標誌 URL** 輸入包含要用於自訂會議邀請的圖像的 URL。

- 說明 **URL** 輸入使用者可取得加入會議協助的網站 URL。

- **法律文字 URL** 輸入具有會議之法律資訊和免責聲明的網站 URL。

- **自訂頁腳文字** 輸入要用於自訂會議邀請的文字。

如需使用會議設定的詳細資訊，請參閱作業文件中的＜[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)＞。 如需針對大型會議設定會議設定的詳細資訊，請參閱規劃檔中的 [設定大型會議的支援](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) 。
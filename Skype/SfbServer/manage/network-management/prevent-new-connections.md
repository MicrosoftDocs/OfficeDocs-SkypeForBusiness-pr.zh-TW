---
title: 防止新的連線
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 2ac97c784f2286a2231a5f20f54aa00daf646384
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600008"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>避免伺服器維護的新連線商務用 Skype Server


商務用 Skype Server 可讓您讓伺服器離線 (例如，套用軟體或硬體升級) ，而不會中斷使用者的任何服務。

當您指定該選項以防止對集區中的伺服器進行新的連線或呼叫時，該選項會在您正式實作這個選項時停止接受任何新的連線與呼叫。這些新的連線和呼叫會路由轉送給集區中的其他伺服器。伺服器會防止新的連線進入，以讓現有連線的工作階段持續進行到自然結束為止。當所有現有的工作階段都結束時，伺服器就可以準備離線。

當您禁止新的前端伺服器連線時，有些商務用 Skype Server 的功能和服務會依賴 DNS 負載平衡，以確保其運作正常。 如果您的集區沒有使用 DNS 負載平衡，透過這些服務進行的連線可能無法在伺服器阻止新的連線傳入期間，由系統重新路由傳送至其他伺服器，因此當該伺服器離線時，有些工作階段及呼叫便會中斷。 以下是仰賴 DNS 負載平衡以確保此選項正常運作的相關功能：

  - 語音應答

  - Conferencing Announcement application

  - 回應群組應用程式

  - 宣告應用程式

  - Call Park application

如需 DNS 負載平衡的詳細資訊，請參閱 [負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。

除了為執行商務用 Skype Server 的伺服器上的所有服務阻止新的連線，您也可以防止個別商務用 Skype Server 服務的新連線。 例如，在您需要套用不需要整個伺服器關閉的商務用 Skype Server 更新的情況下，此方法很有用。 請注意，當您要防止某個服務進行連線，必須選取已經顯示在 Windows 服務清單中的分組服務項目。 例如，商務用 Skype Server Front-End 服務和用於監視的資料收集代理程式是個別的商務用 Skype Server 服務，但是在 Windows 服務清單中，會進行合併，並顯示為商務用 Skype Server 前端服務。 您可以阻止商務用 Skype Server 前端服務的新連線，但無法個別阻止這兩個個別基礎商務用 Skype Server 服務的新連線。

> [!IMPORTANT]
> 設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>若要防止新的連線商務用 Skype Server

1.  以 Administrators 群組成員的身分登入本機電腦。

2.  開啟 [服務] 嵌入式管理單元主控台：按一下 [ **開始**]，指向 [ **所有程式**]，指向 [系統 **管理工具**]，然後按一下 [ **服務**]。

3.  在清單中，按兩下您要防止新連線的商務用 Skype Server Windows 服務。

4.  在 [內容] 對話方塊的 **[服務狀態: 已啟動]** 下方，按一下 **[暫停]**。

5.  (選用，但建議) 按一下 **[啟動類型]** 旁的 **[手動]**。
    
    > [!IMPORTANT]
    > 設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。

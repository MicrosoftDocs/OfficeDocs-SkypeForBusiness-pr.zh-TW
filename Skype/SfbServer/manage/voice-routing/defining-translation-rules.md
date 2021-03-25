---
title: 在商務用 Skype Server 中定義轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server Enterprise Voice 會根據標準化為 e.164 格式的電話號碼，進行呼叫。 這表示所有撥打的字串都必須正常化為 e.164 格式，以執行反向號碼查閱 (RNL) ，使其可轉譯成比對其相符的 SIP URI。 商務用 Skype Server 可讓您操縱所叫的識別碼及來電者識別碼簡報。
ms.openlocfilehash: f3a37a48ec2e4497d644e2051a6e6d37ccef9707
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120905"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>在商務用 Skype Server 中定義轉譯規則

商務用 Skype Server Enterprise Voice 會根據標準化為 e.164 格式的電話號碼，進行呼叫。 這表示所有撥打的字串都必須正常化為 e.164 格式，以執行反向號碼查閱 (RNL) ，使其可轉譯成比對其相符的 SIP URI。 商務用 Skype Server 可讓您操縱所叫的識別碼及來電者識別碼簡報。

在商務用 Skype Server 中，被叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成主幹對等 (（即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) ）所需的本機撥號格式。 若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。

## <a name="caller-id-presentation"></a>來電者識別碼簡報

商務用 Skype 伺服器提供的選項也可轉譯呼叫者的電話號碼 (也就是說，來電者) 撥打的電話號碼是由 e.164 格式所要求的，也就是主幹對等項所需的本機撥號格式。 例如，您可撰寫轉譯規則，來將撥號字串開頭的 +44 移除，並以 0144 來取代。

**使用商務用 Skype Server 控制台設定來電者識別碼**

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [委派設定許可權](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱 [Install and open the 系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 **[語音路由]**，然後按一下 **[主幹組態]**。
4. 在 [主幹組態] 頁面上，按兩下現有的主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。
5. 若要設定來電者 ID 呈現方式：
    - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[來電號碼轉譯規則]** 中，按一下您想要與主幹建立關聯的規則，然後按一下 **[確定]**。
    - 若要定義新的轉譯規則並將其與主幹建立關聯，請按一下 **[新增]**。 
    - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。
    - 若要複製現有的轉譯規則，以做為定義新規則的起點，請按一下規則名稱，按一下 [ **複製**]，然後按一下 [ **貼** 上]。
    - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。

> [!Warning] 
> 如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。 

## <a name="called-id-presentation"></a>稱為識別碼簡報

> [!Important]
> 將一個或多個轉譯規則與企業語音主幹組態建立關聯的功能，主要是作為在主幹對等上設定轉譯規則的 *「替代方法」*。如果您已在主幹對等上設定了轉譯規則，請不要將轉譯規則與企業語音主幹設定相關聯，因為兩種規則可能會衝突。 

您可以使用下列任何一種方法建立或修改轉譯規則：

- 您可以[使用組建轉譯規則工具](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool)，指定起始位數、長度、要移除的位數和要加入的數位的值，然後讓商務用 Skype Server 控制台產生對應的符合模式和轉譯規則。
- [手動寫入正則運算式](#create-or-modify-a-translation-rule-manually) ，以定義相符的模式和轉譯規則。

> [!Note]
> 如需如何撰寫正則運算式的詳細資訊，請參閱 [.Net Framework 正則運算式](/dotnet/standard/base-types/regular-expressions)。 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>使用組建轉譯規則工具建立或修改轉譯規則

若要定義轉譯規則，請在 [組建轉譯規則] 工具中輸入一組值，並啟用商務用 Skype Server 控制台，為您產生對應的相符模式和轉譯規則，以執行下列步驟。 

**使用組建轉譯規則工具定義規則**

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [委派設定許可權](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱 [Install and open the 系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 若要開始定義轉譯規則，請遵循透過步驟 10 [設定具有媒體旁路的主幹](GET LINK AFTER MIGRATION)中的步驟，或在步驟9中 [設定無媒體旁路的主幹](GET LINK AFTER MIGRATION) 。
4. 在 [**新增轉譯規則**] 或 [**編輯轉譯規則**] 頁面的 [**名稱**] 下，輸入描述所轉譯之號碼模式的名稱。
5.  (選用) 在 [ **描述**] 底下，輸入轉譯規則的描述，例如 **美國國際長途撥號**。
6. 在對話方塊的 [ **組建轉譯規則** ] 區段中，于下欄欄位中輸入值：
    - **開始位數**： (選用) 指定您想要模式比對的數位前置位數。 例如，在此欄位中輸入 [+]，以比對以 +) 開頭的 (164 格式的數位。
    - **Length**：指定比對模式中的位數，並選取是否要讓模式比對此長度的數位完全一致、至少此長度或任何長度。 例如，輸入 **11** ， **至少** 在下拉式清單中選取，以比對長度至少為11位數的數位。
    - **要移除的位數**： (選用) 指定要移除的開始數位的數目。 例如，輸入 **1** 以從號碼的開頭去掉 +。
    - **要新增的位數**： (選用) 指定要預先編號為已轉譯之數位的位數。 例如，如果您希望在套用規則時，將011預先加入翻譯的編號，請輸入 **011** 。
    
    您在這些欄位中輸入的值，會反映在 [ **要搭配的模式** ] 和 [ **轉譯** 規則] 欄位中。 例如，如果您指定前面的範例值，則會在 [ **要 matc** h] 欄位的模式中產生正則運算式：
    
    **^\+ ( \d {9} \d +) $** 

    **轉譯規則** 欄位會指定轉譯後的數位格式的模式。 這種模式分為兩個部分：
    - 值 (例如， **$1**) ，代表比對模式中的數位數目
    -  (選用) 您可以在 [ **要加入的數位** ] 欄位中輸入值，以進行前置計算

    使用上述範例值， **011 $ 1** 會出現在 **轉譯規則** 欄位中。
    
    套用此轉譯規則時，+ 441235551010 會變成011441235551010。
7. 按一下 **[確定]** 儲存轉譯規則。
8. 按一下 **[確定]** 儲存主幹組態。
9. 在 [ **主幹 Configuratio** n] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。 

> [!Note]
> 當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。 如需詳細資訊，請參閱 [將擱置的變更發佈至語音路由](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)設定。 

### <a name="create-or-modify-a-translation-rule-manually"></a>手動建立或修改轉譯規則

若要撰寫相符樣式及轉譯規則的規則運算式以定義轉譯規則，請遵循下列步驟。 

**若要手動定義轉譯規則**

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [委派設定許可權](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱 [Install and open the 系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 若要開始定義轉譯規則，請遵循透過步驟 10 [設定具有媒體旁路的主幹](GET LINK AFTER MIGRATION)中的步驟，或在步驟9中 [設定無媒體旁路的主幹](GET LINK AFTER MIGRATION) 。
4. 在 **[新增轉譯規則]** 或 **[編輯轉譯規則]** 頁面的 **[名稱]** 欄位中，輸入可描述所轉譯號碼模式的名稱。
5.  (選用) 在 [ **描述**] 中，輸入轉譯規則的描述;例如， **美國國際長途撥號**。
6. 按一下 **[建置轉譯規則]** 區段底部的 **[編輯]**。
7. 在 [輸入 **正則運算式**] 中輸入下列專案：
    - 在 [符合此模式] 中，指定用來比對要轉譯之號碼的模式。
    - 在 [轉譯規則] 中，指定轉譯號碼的格式模式。

    例如，如果您在 **符合此模式** 的情況下輸入 **^ \+ ( \d {9} \d +) $** 和 **轉譯規則** 中的 **011 $ 1** ，則此規則會將 + 441235551010 轉譯為011441235551010。
8. 按一下 **[確定]** 儲存轉譯規則。
9. 按一下 **[確定]** 儲存主幹組態。
10. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。 

> [!Note] 
> 當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。 如需詳細資訊，請參閱 [將擱置的變更發佈至語音路由](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)設定。
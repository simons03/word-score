<script lang="ts">

    let text = "";


    let totalWords = 0;
    let totalMeningar = 0;
    let wordsLongerThen6Words = 0;
    let total = 0;

    const click = () => {  

        // detta räknar ut tottalt antal ord
        let words = text.split(/\s+/);
        words = words.filter(word => word.length > 0);
        totalWords = words.length;
        // detta räknar ut totalt antal ord slut

        // antal meningar
        // Splitta texten med avgränsare för meningar (. ! ?)
        let sentences = text.split(/[.!?]/);
        
        // Filtrera bort tomma strängar (vid flera på varandra följande avgränsare)
        sentences = sentences.filter(sentence => sentence.trim().length > 0);
        totalMeningar = sentences.length;
        // antal meningar slut

        // antal ord längre än 6 bokstäver
        let wordsMinSix = words.filter(words => words.length > 7);
        wordsLongerThen6Words = wordsMinSix.length;

        // antal ord längre än 6 bokstäver
        // uträkningen 
        const wordDividedSentence = totalWords / totalMeningar;
        const over6AndWords = (wordsLongerThen6Words * 100) / totalWords;
        total = wordDividedSentence + over6AndWords;
    }

</script>


<div class="container mx-auto">
    <div>
        <h1>Enter text here</h1>
        <textarea name="text" id="text" cols="40" rows="5" style="border: 1px solid gray;" class="p-2" bind:value={text}></textarea>
        <div>
            <button class="btn btn-blue" on:click={click}>Get score</button>
        </div>

        <div class="my-5">
            <div>
                <h1>totalWords</h1>
                {totalWords}
            </div>
            <div>
                <h1>totalMeningar</h1>
                {totalMeningar}
            </div>
            <div>
                <h1>wordsLongerThen6Words</h1>
                {wordsLongerThen6Words}
            </div>
            <div>
                <h1>Total score (LIX) </h1>
                {total.toFixed(2)}
            </div>

        </div>
    </div>
</div>



<style>
  .btn {
    @apply font-bold py-2 px-4 rounded;
  }
  .btn-blue {
    @apply bg-blue-500 text-white;
  }
  .btn-blue:hover {
    @apply bg-blue-700;
  }
</style>
<script lang="ts">
    import { onMount } from "svelte";
    import Chart from "chart.js/auto";

    let chart;
    let ctx: HTMLCanvasElement;
    onMount(() => {
        chart = new Chart(ctx, {
            type: "line",
            data: {
                labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
                datasets: [
                    {
                        label: "# of Votes",
                        data: [12, 19, 3, 5, 2, 3],
                        borderWidth: 1,
                        fill: "origin",
                        backgroundColor: "#d9ed92",
                    },
                    {
                        label: "# of Votes",
                        data: [15, 22, 6, 8, 4, 6],
                        borderWidth: 1,
                        fill: "origin",
                        backgroundColor: "#99d98c",
                    },
                ],
            },
            options: {
                aspectRatio: 4/3,
                scales: {
                    y: {
                        beginAtZero: true,
                    },
                },
            },
        });
    });
</script>

<div class="myChart">
    <canvas bind:this={ctx} />
</div>

<style>
    .myChart {
        width: 500px;
        padding: 2em;
    }
</style>

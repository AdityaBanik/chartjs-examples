<script lang="ts">
    import { onMount } from "svelte";
    import Chart from "chart.js/auto";

    let chart;
    let ctx: HTMLCanvasElement;
    onMount(() => {
        chart = new Chart(ctx, {
            type: "bar",
            data: {
                labels: [
                    ["All", "Industrial", "Process"],
                    ["Mineral", "Products"],
                    ["Chemical", "Industry"],
                    ["Metal", "Production"],
                    ["Consumption", "of", "Halocarbons", "and", "SF6"],
                ],
                datasets: [
                    {
                        label: "2010",
                        data: [17000, 3000, 500, 16000, 100],
                        backgroundColor: "#ade8f4",
                        barPercentage: 1.0,
                     
                    },
                    {
                        label: "2012",
                        data: [19000, 2000, 800, 18000,500],
                        backgroundColor: "#48cae4",
                        barPercentage: 1.0,
                       
                    },
                    {
                        label: "2014",
                        data: [15000, 5000, 600, 11000,1000],
                        backgroundColor: "#0077b6",
                        barPercentage: 1.0,
                       
                    },
                ],
            },
            options: {
                aspectRatio: 1, 
                scales: {
                    x: {
                        grid: {
                            display: false, // Remove x-axis grid lines
                        },
                    },
                    y: {
                        grid: {
                            display: false, // Remove y-axis grid lines
                        },
                        beginAtZero: true,
                        suggestedMax: 25000,
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
